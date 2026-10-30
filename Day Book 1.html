<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#1f5f6b">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-title" content="Daybook">
<title>Daybook</title>
<!--
  DAYBOOK — standalone version
  Fill in FIREBASE_CONFIG below (from Firebase console → Project settings → Your apps → Web app).
  Full setup steps are in SETUP.md.
-->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Newsreader:opsz,wght@6..72,500;6..72,600&family=Figtree:wght@400;500;600&family=JetBrains+Mono:wght@500&display=swap">
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-firestore-compat.js"></script>
<style>
:root{
  --bg:#eef1f4; --paper:#ffffff; --ink:#18212b; --muted:#5d6b78; --rule:#d6dde4; --soft:#e3e8ed;
  --accent:#1f5f6b; --accent-ink:#ffffff; --mark:#f2b33d; --danger:#b4412f;
  --idea:#1f5f6b; --thought:#6a4c93; --task:#2f7a3e; --remind:#b06a12;
  --display:"Newsreader",Georgia,"Times New Roman",serif;
  --body:"Figtree",system-ui,-apple-system,"Segoe UI",sans-serif;
  --mono:"JetBrains Mono",ui-monospace,Menlo,Consolas,monospace;
  color-scheme:light;
}
@media (prefers-color-scheme: dark){:root{
  --bg:#12171c; --paper:#1a2129; --ink:#e6ebf0; --muted:#94a3b1; --rule:#2b3540; --soft:#222b34;
  --accent:#5fb3c1; --accent-ink:#0d1a1d; --danger:#e07a68;
  --idea:#5fb3c1; --thought:#b195da; --task:#6cc27c; --remind:#e6a24a; color-scheme:dark}}
*{box-sizing:border-box}
[hidden]{display:none!important}
html,body{margin:0;background:var(--bg);color:var(--ink)}
body{font-family:var(--body);font-size:16px;line-height:1.5;-webkit-tap-highlight-color:transparent;padding-top:env(safe-area-inset-top,0px)}
.wrap{max-width:680px;margin:0 auto;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px));padding-block:18px 0;display:flex;flex-direction:column;gap:16px}
.bottom-space{height:var(--dock-h,120px)}
header{display:flex;justify-content:space-between;align-items:center;gap:12px}
h1{font-family:var(--display);font-weight:600;font-size:1.7rem;line-height:1.1;margin:0}
.today{font-family:var(--mono);font-size:.72rem;color:var(--muted);letter-spacing:.05em;text-transform:uppercase}
.who{display:flex;align-items:center;gap:8px}
.sync{font-size:.75rem;color:var(--muted);display:flex;align-items:center;gap:6px;white-space:nowrap}
.dot{width:8px;height:8px;border-radius:50%;background:var(--muted)}
.dot.on{background:var(--task)}
.avatar{width:32px;height:32px;border-radius:50%;border:1px solid var(--rule);background:var(--soft);cursor:pointer;padding:0;overflow:hidden;font:inherit;font-weight:600;color:var(--ink)}
.avatar img{width:100%;height:100%;object-fit:cover;display:block}
.menu{position:absolute;right:max(16px,env(safe-area-inset-right,0px));top:calc(64px + env(safe-area-inset-top,0px));background:var(--paper);border:1px solid var(--rule);border-radius:12px;padding:8px;display:flex;flex-direction:column;gap:4px;z-index:30;min-width:220px;box-shadow:0 8px 24px rgb(0 0 0 / .12)}
.menu .em{font-size:.8rem;color:var(--muted);padding:4px 8px 8px;border-bottom:1px solid var(--rule);overflow-wrap:anywhere}
.menu button{border:none;background:transparent;color:var(--ink);font:inherit;text-align:left;padding:10px 8px;border-radius:8px;cursor:pointer}
.menu button:hover{background:var(--soft)}

/* login */
.login{min-height:100vh;min-height:100dvh;display:grid;place-items:center;padding:24px max(16px,env(safe-area-inset-left,0px))}
.card{background:var(--paper);border:1px solid var(--rule);border-radius:18px;padding:28px 24px;max-width:380px;width:100%;display:flex;flex-direction:column;gap:14px}
.card h1{font-size:2.2rem}
.card p{margin:0;color:var(--muted)}
.gbtn{display:flex;align-items:center;justify-content:center;gap:10px;min-height:48px;border-radius:12px;border:1px solid var(--rule);background:var(--paper);color:var(--ink);font:inherit;font-weight:600;cursor:pointer}
.gbtn svg{width:20px;height:20px}
.err{color:var(--danger);font-size:.9rem}
.card code{font-family:var(--mono);font-size:.8rem;background:var(--soft);padding:1px 5px;border-radius:4px}

/* calendar strip */
.calstrip{display:flex;flex-direction:column;gap:8px}
.calhead{display:flex;align-items:baseline;justify-content:space-between;gap:8px}
.label{font-family:var(--mono);font-size:.7rem;text-transform:uppercase;letter-spacing:.07em;color:var(--muted)}
.calhead a{font-size:.8rem;color:var(--accent);text-decoration:none}
.events{display:flex;gap:8px;overflow-x:auto;padding-bottom:4px;scroll-snap-type:x mandatory;scrollbar-width:none}
.events::-webkit-scrollbar{display:none}
.ev{flex:0 0 auto;scroll-snap-align:start;background:var(--paper);border:1px solid var(--rule);border-radius:12px;padding:8px 12px;min-width:132px;max-width:220px;text-decoration:none;color:var(--ink)}
.ev .t{font-family:var(--mono);font-size:.72rem;color:var(--accent)}
.ev .s{font-size:.9rem;font-weight:500;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.ev.tmr .t{color:var(--muted)}
.calmsg{font-size:.85rem;color:var(--muted);background:var(--paper);border:1px dashed var(--rule);border-radius:12px;padding:10px 12px;display:flex;gap:10px;align-items:center;flex-wrap:wrap}
.calmsg button{border:none;background:var(--accent);color:var(--accent-ink);font:inherit;font-size:.82rem;font-weight:600;min-height:32px;padding:0 12px;border-radius:8px;cursor:pointer}

/* search + filters */
.tools{display:flex;flex-direction:column;gap:8px}
input[type=search]{width:100%;font:inherit;font-size:16px;color:var(--ink);background:var(--paper);border:1px solid var(--rule);border-radius:12px;padding:10px 12px}
.scroller{display:flex;gap:6px;overflow-x:auto;scrollbar-width:none;padding-bottom:2px}
.scroller::-webkit-scrollbar{display:none}
.chip{flex:0 0 auto;border:1px solid var(--rule);background:var(--paper);color:var(--ink);font:inherit;font-size:.88rem;min-height:36px;padding:0 14px;border-radius:999px;cursor:pointer;display:inline-flex;align-items:center;gap:6px}
.chip i{width:8px;height:8px;border-radius:50%;display:inline-block}
.chip[aria-pressed="true"]{border-color:var(--ink);background:var(--ink);color:var(--paper)}
.chip.dl{margin-left:auto}

/* list */
.day{display:flex;flex-direction:column}
.dayhead{position:sticky;top:0;z-index:2;background:var(--bg);display:flex;align-items:baseline;gap:10px;padding:8px 0 6px;border-bottom:1px solid var(--rule)}
.dayhead h2{font-family:var(--display);font-weight:500;font-size:1.2rem;margin:0}
.dayhead span{font-family:var(--mono);font-size:.72rem;color:var(--muted)}
.dayhead .count{margin-left:auto}
.note{display:grid;grid-template-columns:auto 1fr;gap:4px 10px;padding:12px 2px;border-bottom:1px dashed var(--rule)}
.note:last-child{border-bottom:none}
.tag{font-family:var(--mono);font-size:.66rem;text-transform:uppercase;letter-spacing:.06em;padding:2px 7px;border-radius:4px;border:1px solid currentColor;margin-top:3px;white-space:nowrap;align-self:start}
.k-idea{color:var(--idea)}.k-thought{color:var(--thought)}.k-task{color:var(--task)}.k-reminder{color:var(--remind)}
.txt{min-width:0;white-space:pre-wrap;overflow-wrap:anywhere}
.txt.done{text-decoration:line-through;color:var(--muted)}
.under{grid-column:2;display:flex;flex-wrap:wrap;align-items:center;gap:4px 12px;font-family:var(--mono);font-size:.72rem;color:var(--muted)}
.under a{color:var(--accent);text-decoration:none}
.under .sp{flex:1}
.act{border:none;background:var(--soft);color:var(--ink);font:inherit;font-family:var(--body);font-size:.82rem;min-height:32px;padding:0 12px;border-radius:8px;cursor:pointer}
.act.del{color:var(--danger)}
.act.yes{background:var(--danger);color:var(--paper)}
.empty{background:var(--paper);border:1px dashed var(--rule);border-radius:14px;padding:20px;color:var(--muted)}
.empty b{color:var(--ink);font-family:var(--display);font-size:1.1rem;font-weight:500;display:block;margin-bottom:4px}

/* docked composer */
.dock{position:fixed;left:0;right:0;bottom:0;z-index:5;background:color-mix(in srgb,var(--bg) 88%,transparent);backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);border-top:1px solid var(--rule);padding-left:max(12px,env(safe-area-inset-left,0px));padding-right:max(12px,env(safe-area-inset-right,0px));padding-top:10px;padding-bottom:calc(10px + env(safe-area-inset-bottom,0px))}
.dock form{max-width:680px;margin:0 auto;display:flex;flex-direction:column;gap:10px}
.bar{display:flex;gap:8px;align-items:flex-end}
textarea{flex:1;min-width:0;min-height:46px;max-height:40vh;resize:none;border:1px solid var(--rule);outline:none;background:var(--paper);color:var(--ink);font:inherit;font-size:16px;line-height:1.4;border-radius:14px;padding:11px 14px}
.send{flex:0 0 auto;width:46px;height:46px;border:none;border-radius:50%;background:var(--accent);color:var(--accent-ink);cursor:pointer;display:grid;place-items:center}
.send:disabled{opacity:.45}
.send svg{width:20px;height:20px}
.opts{display:flex;flex-direction:column;gap:8px}
.dock:not(.open) .opts{display:none}
.optrow{display:flex;gap:6px;align-items:center;overflow-x:auto;scrollbar-width:none}
.optrow::-webkit-scrollbar{display:none}
input[type=date],input[type=time]{font:inherit;font-size:16px;color:var(--ink);background:var(--paper);border:1px solid var(--rule);border-radius:999px;min-height:36px;padding:0 10px}
.toggle{flex:0 0 auto;display:inline-flex;align-items:center;gap:8px;min-height:36px;padding:0 14px;border-radius:999px;border:1px solid var(--rule);background:var(--paper);font-size:.88rem;cursor:pointer;user-select:none}
.toggle input{width:18px;height:18px;accent-color:var(--accent);margin:0}
.toggle:has(input:checked){border-color:var(--accent);color:var(--accent)}
button:focus-visible,input:focus-visible,textarea:focus-visible,a:focus-visible{outline:2px solid var(--accent);outline-offset:2px}
.toast{position:fixed;left:50%;transform:translateX(-50%);bottom:calc(var(--dock-h,120px) + 10px);background:var(--ink);color:var(--paper);padding:8px 14px;border-radius:10px;font-size:.88rem;z-index:20;max-width:calc(100% - 32px);text-align:center}
@media (prefers-reduced-motion:no-preference){.note{animation:in .3s ease-out}}
@keyframes in{from{background:color-mix(in srgb,var(--mark) 25%,transparent)}to{background:transparent}}
@media (min-width:700px){h1{font-size:2rem}.wrap{padding-block:28px 0}}
</style>
</head>
<body>

<!-- ============ LOGIN ============ -->
<section class="login" id="loginView" hidden>
  <div class="card">
    <div class="today" id="loginDate"></div>
    <h1>Daybook</h1>
    <p>Your ideas, thoughts and tasks, date-wise, on every device.</p>
    <button class="gbtn" id="signin" type="button">
      <svg viewBox="0 0 48 48"><path fill="#FFC107" d="M43.6 20.5H42V20H24v8h11.3C33.7 32.7 29.2 36 24 36c-6.6 0-12-5.4-12-12s5.4-12 12-12c3.1 0 5.8 1.2 7.9 3.1l5.7-5.7C34 6.1 29.3 4 24 4 12.9 4 4 12.9 4 24s8.9 20 20 20 20-8.9 20-20c0-1.3-.1-2.4-.4-3.5z"/><path fill="#FF3D00" d="M6.3 14.7l6.6 4.8C14.7 15.1 19 12 24 12c3.1 0 5.8 1.2 7.9 3.1l5.7-5.7C34 6.1 29.3 4 24 4 16.3 4 9.7 8.3 6.3 14.7z"/><path fill="#4CAF50" d="M24 44c5.2 0 9.9-2 13.4-5.2l-6.2-5.2C29.2 35.1 26.7 36 24 36c-5.2 0-9.6-3.3-11.3-8l-6.5 5C9.5 39.6 16.2 44 24 44z"/><path fill="#1976D2" d="M43.6 20.5H42V20H24v8h11.3c-.8 2.2-2.2 4.2-4.1 5.6l6.2 5.2C37 39.2 44 34 44 24c0-1.3-.1-2.4-.4-3.5z"/></svg>
      Sign in with Google
    </button>
    <div class="err" id="loginErr" hidden></div>
  </div>
</section>

<!-- ============ APP ============ -->
<div id="appView" hidden>
<div class="wrap">
  <header>
    <div>
      <div class="today" id="today"></div>
      <h1>Daybook</h1>
    </div>
    <div class="who">
      <div class="sync"><span class="dot" id="dot"></span><span id="syncText">Connecting…</span></div>
      <button class="avatar" id="avatar" type="button" aria-label="Account"></button>
    </div>
  </header>
  <div class="menu" id="menu" hidden>
    <div class="em" id="menuEmail"></div>
    <button type="button" id="dlBtn">Download all notes</button>
    <button type="button" id="signout">Sign out</button>
  </div>

  <section class="calstrip" aria-label="Calendar">
    <div class="calhead"><span class="label">Today &amp; tomorrow</span><a id="calOpen" href="https://calendar.google.com/calendar/r/day" target="_blank" rel="noopener">Open calendar ↗</a></div>
    <div class="events" id="events"><div class="calmsg">Loading your calendar…</div></div>
  </section>

  <div class="tools">
    <input type="search" id="q" placeholder="Search notes" aria-label="Search notes">
    <div class="scroller" id="filters" role="group" aria-label="Filter"></div>
  </div>

  <main id="list"></main>
  <div class="bottom-space"></div>
</div>

<div class="dock" id="dock">
  <form id="form" autocomplete="off">
    <div class="opts">
      <div class="optrow" id="kinds" role="group" aria-label="Type"></div>
      <div class="optrow" id="when" role="group" aria-label="Date">
        <button type="button" class="chip" data-d="0">Today</button>
        <button type="button" class="chip" data-d="1">Tomorrow</button>
        <input type="date" id="date" aria-label="Pick date">
        <input type="time" id="time" aria-label="Time (optional)">
        <label class="toggle"><input type="checkbox" id="toCal"> Calendar</label>
      </div>
    </div>
    <div class="bar">
      <textarea id="text" rows="1" placeholder="Write an idea, thought or task…" aria-label="Note"></textarea>
      <button class="send" id="save" type="submit" aria-label="Save note" disabled>
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M12 19V5M5 12l7-7 7 7"/></svg>
      </button>
    </div>
  </form>
</div>
</div>
<div class="toast" id="toast" hidden></div>

<script>
/* ================= CONFIG — fill these in ================= */
const FIREBASE_CONFIG = {
  apiKey: "PASTE_API_KEY",
  authDomain: "PASTE_PROJECT_ID.firebaseapp.com",
  projectId: "PASTE_PROJECT_ID",
  appId: "PASTE_APP_ID"
};
// Only these Google accounts can use the app (must match the Firestore rules in SETUP.md)
const ALLOWED_EMAILS = ["letsbeatthetop@gmail.com"];
const TIMEZONE = "Asia/Kolkata";
/* ========================================================== */

const KINDS=[{id:"idea",label:"Idea"},{id:"thought",label:"Thought"},{id:"task",label:"Task"},{id:"reminder",label:"Reminder"}];
const CAL_SCOPE="https://www.googleapis.com/auth/calendar.events";
const CAL_API="https://www.googleapis.com/calendar/v3/calendars/primary/events";
let kind="idea", filter="all", notes=[], col=null, pendingDel=null, unsub=null, me=null;
const $=id=>document.getElementById(id);
const pad=n=>String(n).padStart(2,"0");
const iso=d=>d.getFullYear()+"-"+pad(d.getMonth()+1)+"-"+pad(d.getDate());
const addDays=(ds,n)=>{const d=new Date(ds+"T00:00");d.setDate(d.getDate()+n);return iso(d)};
const todayIso=()=>iso(new Date());
const store={get:k=>{try{return localStorage.getItem(k)}catch(e){return null}},set:(k,v)=>{try{localStorage.setItem(k,v)}catch(e){}},del:k=>{try{localStorage.removeItem(k)}catch(e){}}};
const dateLabel=new Date().toLocaleDateString(undefined,{weekday:"short",day:"numeric",month:"short",year:"numeric"});
$("today").textContent=dateLabel;$("loginDate").textContent=dateLabel;

function toast(m){const t=$("toast");t.textContent=m;t.hidden=false;clearTimeout(toast.t);toast.t=setTimeout(()=>t.hidden=true,2800)}
function loginError(m){const e=$("loginErr");e.innerHTML="";e.append(m);e.hidden=false}

/* ================= FIREBASE / AUTH ================= */
const configured=!Object.values(FIREBASE_CONFIG).some(v=>String(v).includes("PASTE_"));
if(!configured){
  $("loginView").hidden=false;$("signin").disabled=true;
  loginError("Setup needed: paste your Firebase config into this file (see SETUP.md).");
  throw new Error("Daybook: Firebase config missing");
}
firebase.initializeApp(FIREBASE_CONFIG);
const auth=firebase.auth(), fs=firebase.firestore();
fs.enablePersistence({synchronizeTabs:true}).catch(()=>{}); // works offline, syncs when back online
auth.setPersistence(firebase.auth.Auth.Persistence.LOCAL);   // stay signed in on this device

function provider(){const p=new firebase.auth.GoogleAuthProvider();p.addScope(CAL_SCOPE);p.setCustomParameters({login_hint:ALLOWED_EMAILS[0]||"",prompt:"select_account"});return p}
function keepToken(result){
  const cred=result&&result.credential;
  if(cred&&cred.accessToken){store.set("daybook-gtoken",JSON.stringify({t:cred.accessToken,exp:Date.now()+55*60000}))}
}
function token(){try{const o=JSON.parse(store.get("daybook-gtoken")||"null");return o&&o.exp>Date.now()?o.t:null}catch(e){return null}}

async function signIn(){
  $("loginErr").hidden=true;
  try{keepToken(await auth.signInWithPopup(provider()))}
  catch(e){
    if(e.code==="auth/popup-blocked"||e.code==="auth/operation-not-supported-in-this-environment"){auth.signInWithRedirect(provider());return}
    if(e.code==="auth/popup-closed-by-user"||e.code==="auth/cancelled-popup-request")return;
    if(e.code==="auth/unauthorized-domain")return loginError("This web address isn't allowed yet. Add it under Firebase → Authentication → Settings → Authorized domains.");
    loginError("Sign-in failed: "+(e.message||e.code));
  }
}
auth.getRedirectResult().then(keepToken).catch(e=>{if(e&&e.code)loginError("Sign-in failed: "+(e.message||e.code))});
$("signin").onclick=signIn;

auth.onAuthStateChanged(async u=>{
  if(unsub){unsub();unsub=null}
  if(!u){me=null;col=null;notes=[];$("appView").hidden=true;$("loginView").hidden=false;return}
  if(!ALLOWED_EMAILS.includes((u.email||"").toLowerCase())){
    await auth.signOut();store.del("daybook-gtoken");
    $("appView").hidden=true;$("loginView").hidden=false;
    loginError(u.email+" isn't allowed to use this Daybook. Sign in with "+ALLOWED_EMAILS.join(" or ")+".");return;
  }
  me=u;$("loginView").hidden=true;$("appView").hidden=false;
  $("menuEmail").textContent=u.email;$("calOpen").href="https://calendar.google.com/calendar/u/"+encodeURIComponent(u.email)+"/r/day";
  const av=$("avatar");av.innerHTML="";
  if(u.photoURL){const i=document.createElement("img");i.src=u.photoURL;i.alt="";i.referrerPolicy="no-referrer";av.append(i)}else av.textContent=(u.email||"?")[0].toUpperCase();
  col=fs.collection("users").doc(u.uid).collection("notes");
  unsub=col.orderBy("createdAt","desc").onSnapshot({includeMetadataChanges:true},s=>{
    notes=s.docs.map(d=>({id:d.id,...d.data()})).filter(n=>n.text);
    const off=s.metadata.fromCache;$("dot").classList.toggle("on",!off);$("syncText").textContent=off?"Offline · saved on device":"Synced";
    render();
  },e=>{$("dot").classList.remove("on");$("syncText").textContent=e.code==="permission-denied"?"No access — check rules":"Sync error"});
  setDockH();loadCalendar();
});

$("avatar").onclick=e=>{e.stopPropagation();$("menu").hidden=!$("menu").hidden};
document.addEventListener("click",e=>{if(!$("menu").contains(e.target))$("menu").hidden=true});
$("signout").onclick=async()=>{$("menu").hidden=true;store.del("daybook-gtoken");await auth.signOut()};

/* ================= GOOGLE CALENDAR ================= */
async function reconnectCalendar(){
  try{keepToken(await me.reauthenticateWithPopup(provider()));loadCalendar();return true}
  catch(e){
    if(e.code==="auth/popup-blocked"){auth.signInWithRedirect(provider());return false}
    if(e.code!=="auth/popup-closed-by-user")toast("Couldn't connect Google Calendar: "+(e.message||e.code));return false;
  }
}
async function gcal(method,url,body){
  const t=token();if(!t)throw{code:"no_token"};
  const r=await fetch(url,{method,headers:{Authorization:"Bearer "+t,"Content-Type":"application/json"},body:body?JSON.stringify(body):undefined});
  if(r.status===401){store.del("daybook-gtoken");throw{code:"no_token"}}
  if(r.status===403)throw{code:"forbidden",message:"Calendar access denied. Check that the Google Calendar API is enabled (SETUP.md step 4)."};
  if(!r.ok)throw{code:"http",message:"Google Calendar error "+r.status};
  return r.json();
}
function calMsg(text,withBtn){
  const box=$("events");box.innerHTML="";const d=document.createElement("div");d.className="calmsg";
  const s=document.createElement("span");s.textContent=text;d.append(s);
  if(withBtn){const b=document.createElement("button");b.type="button";b.textContent="Connect calendar";b.onclick=reconnectCalendar;d.append(b)}
  box.append(d);
}
function fmtTime(s){if(!s)return"";if(s.date)return"All day";const d=new Date(s.dateTime);return pad(d.getHours())+":"+pad(d.getMinutes())}
async function loadCalendar(){
  if(!token())return calMsg("Show today's events and add notes to your calendar.",true);
  const t=todayIso();
  const p=new URLSearchParams({timeMin:new Date(t+"T00:00").toISOString(),timeMax:new Date(addDays(t,2)+"T00:00").toISOString(),singleEvents:"true",orderBy:"startTime",maxResults:"25"});
  try{
    const data=await gcal("GET",CAL_API+"?"+p);
    const box=$("events");box.innerHTML="";
    const ev=(data.items||[]).filter(e=>e.status!=="cancelled");
    if(!ev.length)return calMsg("Nothing on your calendar today or tomorrow.");
    const tm=addDays(t,1);
    ev.forEach(e=>{
      const day=e.start?.date||(e.start?.dateTime?iso(new Date(e.start.dateTime)):"");
      const a=document.createElement("a");a.className="ev"+(day===tm?" tmr":"");a.href=e.htmlLink||"#";a.target="_blank";a.rel="noopener";
      const tt=document.createElement("div");tt.className="t";tt.textContent=(day===tm?"Tmrw · ":"")+fmtTime(e.start);
      const s=document.createElement("div");s.className="s";s.textContent=e.summary||"(No title)";
      a.append(tt,s);box.append(a);
    });
  }catch(e){
    if(e.code==="no_token")calMsg("Calendar connection expired.",true);
    else calMsg(e.message||"Calendar is unavailable right now.");
  }
}
setInterval(()=>{if(me&&!document.hidden&&token())loadCalendar()},5*60000);
document.addEventListener("visibilitychange",()=>{if(!document.hidden&&me)loadCalendar()});

function calTitle(n){return (KINDS.find(k=>k.id===n.kind)?.label||"Note")+": "+n.text.split("\n")[0].slice(0,80)}
function eventBody(n){
  const b={summary:calTitle(n),description:n.text,reminders:{useDefault:true}};
  if(n.time){
    const [h,m]=n.time.split(":").map(Number);const end=new Date(2000,0,1,h,m+30);
    const endDate=end.getDate()===2?addDays(n.date,1):n.date;
    b.start={dateTime:n.date+"T"+n.time+":00",timeZone:TIMEZONE};
    b.end={dateTime:endDate+"T"+pad(end.getHours())+":"+pad(end.getMinutes())+":00",timeZone:TIMEZONE};
  }else{b.start={date:n.date};b.end={date:addDays(n.date,1)}}
  return b;
}
async function pushToCalendar(n,ref){
  if(!token()){const ok=await reconnectCalendar();if(!ok||!token()){toast("Note saved. Connect your calendar, then tap + Calendar on the note.");return false}}
  try{
    const ev=await gcal("POST",CAL_API,eventBody(n));
    await ref.update({cal:true,calLink:ev.htmlLink||"",calId:ev.id||""});
    loadCalendar();return true;
  }catch(e){toast("Note saved, but the event wasn't created. "+(e.message||"Try + Calendar again."));return false}
}

/* ================= COMPOSER ================= */
const dock=$("dock"),ta=$("text");
function setDockH(){document.documentElement.style.setProperty("--dock-h",dock.offsetHeight+16+"px")}
function grow(){ta.style.height="auto";ta.style.height=Math.min(ta.scrollHeight,window.innerHeight*.4)+"px";$("save").disabled=!ta.value.trim();setDockH()}
function openDock(o){dock.classList.toggle("open",o);setDockH()}
ta.addEventListener("focus",()=>openDock(true));
ta.addEventListener("input",()=>{grow();store.set("daybook-draft",ta.value)});
ta.addEventListener("keydown",e=>{if(e.key==="Enter"&&(e.ctrlKey||e.metaKey)){e.preventDefault();$("form").requestSubmit()}});
document.addEventListener("pointerdown",e=>{if(!dock.contains(e.target)&&!ta.value.trim())openDock(false)});
window.addEventListener("resize",setDockH);
ta.value=store.get("daybook-draft")||"";

function chips(el,list,cur,onPick){
  el.querySelectorAll(".chip:not([data-d])").forEach(c=>c.remove());
  const frag=document.createDocumentFragment();
  list.forEach(k=>{const b=document.createElement("button");b.type="button";b.className="chip";
    b.setAttribute("aria-pressed",k.id===cur);
    if(k.id!=="all"){const i=document.createElement("i");i.style.background=`var(--${k.id==="reminder"?"remind":k.id})`;b.append(i)}
    b.append(k.label);b.onclick=()=>onPick(k.id);frag.append(b)});
  el.prepend(frag);
}
function drawKinds(){chips($("kinds"),KINDS,kind,id=>{kind=id;drawKinds()})}
function drawFilters(){chips($("filters"),[{id:"all",label:"All"},...KINDS],filter,id=>{filter=id;drawFilters();render()})}
drawKinds();drawFilters();
$("date").value=todayIso();
function drawWhen(){const v=$("date").value;document.querySelectorAll("#when [data-d]").forEach(b=>b.setAttribute("aria-pressed",addDays(todayIso(),+b.dataset.d)===v))}
document.querySelectorAll("#when [data-d]").forEach(b=>b.onclick=()=>{$("date").value=addDays(todayIso(),+b.dataset.d);drawWhen()});
$("date").addEventListener("change",drawWhen);drawWhen();grow();

$("form").addEventListener("submit",async e=>{
  e.preventDefault();
  const text=ta.value.trim();if(!text||!col)return;
  const n={text,kind,date:$("date").value||todayIso(),time:$("time").value||"",done:false,createdAt:Date.now(),cal:false};
  const wantCal=$("toCal").checked;
  const ref=col.doc();
  ref.set(n).catch(()=>toast("Couldn't save to the cloud. It will retry when you're back online.")); // resolves instantly offline
  ta.value="";$("time").value="";$("toCal").checked=false;store.del("daybook-draft");grow();ta.focus();
  if(wantCal){if(await pushToCalendar(n,ref))toast("Saved and added to Google Calendar")}else toast("Saved");
});

/* ================= LIST ================= */
$("q").addEventListener("input",render);
function fmtDay(ds){
  const t=todayIso();if(ds===t)return"Today";if(ds===addDays(t,-1))return"Yesterday";if(ds===addDays(t,1))return"Tomorrow";
  return new Date(ds+"T00:00").toLocaleDateString(undefined,{weekday:"long",day:"numeric",month:"short"});
}
function render(){
  const list=$("list");list.innerHTML="";
  const q=$("q").value.trim().toLowerCase();
  const shown=notes.filter(n=>(filter==="all"||n.kind===filter)&&(!q||n.text.toLowerCase().includes(q)));
  const empty=(t,b)=>{list.innerHTML='<div class="empty"><b></b><span></span></div>';list.querySelector("b").textContent=t;list.querySelector("span").textContent=b};
  if(!notes.length)return empty("Your daybook is empty","Type in the box at the bottom and tap the arrow. Notes from your phone and laptop land here, grouped by date.");
  if(!shown.length)return empty("No matches","Try another word, or switch the filter back to All.");
  const groups={};shown.forEach(n=>(groups[n.date]??=[]).push(n));
  Object.keys(groups).sort().reverse().forEach(ds=>{
    const sec=document.createElement("section");sec.className="day";
    const items=groups[ds].sort((a,b)=>(a.time||"99").localeCompare(b.time||"99")||b.createdAt-a.createdAt);
    sec.innerHTML=`<div class="dayhead"><h2></h2><span>${ds}</span><span class="count">${items.length} ${items.length===1?"note":"notes"}</span></div>`;
    sec.querySelector("h2").textContent=fmtDay(ds);
    items.forEach(n=>sec.append(row(n)));list.append(sec);
  });
}
function btn(label,cls,fn){const b=document.createElement("button");b.type="button";b.className="act "+(cls||"");b.textContent=label;b.onclick=fn;return b}
function row(n){
  const el=document.createElement("div");el.className="note";
  const tag=document.createElement("span");tag.className="tag k-"+n.kind;tag.textContent=(KINDS.find(k=>k.id===n.kind)||{label:"Note"}).label;
  const t=document.createElement("div");t.className="txt"+(n.done?" done":"");t.textContent=n.text;
  const u=document.createElement("div");u.className="under";
  const meta=document.createElement("span");meta.textContent=(n.time?n.time+" · ":"")+new Date(n.createdAt).toLocaleTimeString(undefined,{hour:"2-digit",minute:"2-digit"});u.append(meta);
  if(n.cal){const a=document.createElement("a");a.textContent="✓ in calendar";a.href=n.calLink||"https://calendar.google.com/";a.target="_blank";a.rel="noopener";u.append(a)}
  const sp=document.createElement("span");sp.className="sp";u.append(sp);
  if(pendingDel===n.id){
    u.append(btn("Delete","yes",()=>{pendingDel=null;col.doc(n.id).delete().catch(()=>toast("Couldn't delete. Try again."));toast("Deleted")}),btn("Keep","",()=>{pendingDel=null;render()}));
  }else{
    if(n.kind==="task")u.append(btn(n.done?"Undo":"Done","",()=>col.doc(n.id).update({done:!n.done}).catch(()=>toast("Couldn't update."))));
    if(!n.cal)u.append(btn("+ Calendar","",async e=>{e.target.disabled=true;if(await pushToCalendar(n,col.doc(n.id)))toast("Added to Google Calendar");e.target.disabled=false}));
    u.append(btn("Delete","del",()=>{pendingDel=n.id;render()}));
  }
  el.append(tag,t,u);return el;
}

/* ================= DOWNLOAD ================= */
$("dlBtn").onclick=()=>{
  $("menu").hidden=true;
  const by={};notes.forEach(n=>(by[n.date]??=[]).push(n));
  let out="DAYBOOK\n\n";
  Object.keys(by).sort().reverse().forEach(d=>{out+="== "+d+" ==\n";by[d].forEach(n=>{out+=`[${n.kind}]${n.time?" "+n.time:""}${n.done?" (done)":""} ${n.text}\n`});out+="\n"});
  const a=document.createElement("a");a.href=URL.createObjectURL(new Blob([out],{type:"text/plain"}));a.download="daybook-"+todayIso()+".txt";a.click();
  setTimeout(()=>URL.revokeObjectURL(a.href),2000);
};
</script>
</body>
</html>
