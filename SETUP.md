# Daybook setup (about 15 minutes, all free)

Daybook is one file, `index.html`. It needs a free Firebase project for the Google login and for storing your notes, and a web address to live at (GitHub Pages).

## 1. Create a Firebase project
1. Go to https://console.firebase.google.com and sign in with **letsbeatthetop@gmail.com**.
2. **Add project** → name it `daybook` → you can turn Google Analytics off → **Create**.

## 2. Turn on Google sign-in
1. **Build → Authentication → Get started**.
2. **Sign-in method → Google → Enable**, pick your email as support email, **Save**.
3. **Settings → Authorized domains → Add domain** and add the address where Daybook will live, for example `YOUR-GITHUB-USERNAME.github.io`.

## 3. Turn on the notes database
1. **Build → Firestore Database → Create database** → choose a location near you (`asia-south1` Mumbai) → **Start in production mode**.
2. Open the **Rules** tab, replace everything with this, then **Publish**:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid}/{document=**} {
      allow read, write: if request.auth != null
        && request.auth.uid == uid
        && request.auth.token.email == "letsbeatthetop@gmail.com";
    }
  }
}
```
Only you, signed in with that Google account, can read or write your notes.

## 4. Allow Google Calendar access
1. Open https://console.cloud.google.com and pick the project with the same name as your Firebase project.
2. **APIs & Services → Library** → search **Google Calendar API** → **Enable**.
3. **APIs & Services → OAuth consent screen** (or **Google Auth Platform → Audience**): keep it as **External / Testing**, and under **Test users** add **letsbeatthetop@gmail.com**.
4. Under **Data access / Scopes**, add `.../auth/calendar.events`.

When you sign in, Google will show "Google hasn't verified this app". That's expected for a personal app: tap **Continue**.

## 5. Paste your config into index.html
1. Firebase console → ⚙ **Project settings → General → Your apps → Web (</>)** → register an app called `daybook` (no hosting needed).
2. Copy the `apiKey`, `authDomain`, `projectId` and `appId` values into `FIREBASE_CONFIG` near the bottom of `index.html`.

These values are not passwords; they're safe to put on a public page. Your notes are protected by the rules in step 3.

## 6. Put it online
Upload `index.html` to a GitHub repository with Pages turned on (**Settings → Pages → Deploy from branch → main / root**). Your app will be at `https://YOUR-GITHUB-USERNAME.github.io/daybook/`. Make sure that domain is in step 2.3.

## 7. Use it daily
- **Phone:** open the address in Chrome (Android) or Safari (iPhone) → menu → **Add to Home Screen**. It opens like an app and stays signed in.
- **Laptop:** open the address and bookmark it, or in Chrome use ⋮ → **Cast, save and share → Install page as app**.
- Works offline: notes save on the device and sync when you're back online.
- The calendar connection lasts an hour at a time; when it expires, tap **Connect calendar** once.
