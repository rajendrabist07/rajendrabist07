<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Rajendra Bist — Full-Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700;800&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–cyan: #5ef0f0;
–purple: #b48eff;
–pink: #ff6eb4;
–bg: #06060e;
–surface: rgba(255,255,255,0.03);
–border: rgba(255,255,255,0.07);
–text: #d8d8e8;
–muted: #55556a;
}

html { scroll-behavior: smooth; }

body {
background: var(–bg);
color: var(–text);
font-family: ‘Sora’, sans-serif;
min-height: 100vh;
overflow-x: hidden;
line-height: 1.6;
}

/* ── BG FX ── */
.bg-orb {
position: fixed; border-radius: 50%;
pointer-events: none; filter: blur(100px); opacity: .10;
}
.orb-1 { width:700px;height:700px;background:var(–cyan);  top:-250px;right:-250px; }
.orb-2 { width:600px;height:600px;background:var(–purple);bottom:-200px;left:-200px; }
.orb-3 { width:300px;height:300px;background:var(–pink);  top:50%;left:40%;transform:translate(-50%,-50%); }

.noise {
position:fixed;inset:0;pointer-events:none;z-index:0;opacity:.03;
background-image:url(“data:image/svg+xml,%3Csvg viewBox=‘0 0 256 256’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cfilter id=‘n’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=’.9’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘100%25’ height=‘100%25’ filter=‘url(%23n)’/%3E%3C/svg%3E”);
background-size:200px;
}

/* ── LAYOUT ── */
.wrap {
max-width: 760px;
margin: 0 auto;
padding: 64px 24px 96px;
position: relative; z-index: 1;
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
from { opacity:0; transform:translateY(28px); }
to   { opacity:1; transform:translateY(0); }
}
@keyframes pulse { 0%,100%{transform:scale(1);opacity:1} 50%{transform:scale(1.4);opacity:.5} }
@keyframes spin  { to { transform:rotate(360deg); } }
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }
@keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)} }

.fade { animation: fadeUp .7s ease both; }
.d1  { animation-delay:.05s }
.d2  { animation-delay:.18s }
.d3  { animation-delay:.30s }
.d4  { animation-delay:.42s }
.d5  { animation-delay:.54s }
.d6  { animation-delay:.66s }

/* ── HERO ── */
.hero { text-align:center; margin-bottom:56px; }

.avatar-wrap {
display:inline-block; margin-bottom:22px;
animation: float 4s ease-in-out infinite;
}
.avatar-ring {
background: conic-gradient(from 0deg, var(–cyan), var(–purple), var(–pink), var(–cyan));
padding: 3px; border-radius:50%;
animation: spin 8s linear infinite;
}
.avatar-inner {
background: var(–bg); border-radius:50%; padding:5px;
}
.avatar-emoji {
width:90px; height:90px; border-radius:50%;
background: linear-gradient(135deg,#111128,#1a1a38);
display:flex; align-items:center; justify-content:center;
font-size:38px;
}

.status-badge {
display:inline-flex; align-items:center; gap:8px;
padding:6px 18px; border-radius:100px;
background:rgba(34,197,94,.09); border:1px solid rgba(34,197,94,.25);
font-size:11px; letter-spacing:.07em; color:#22c55e; font-weight:600;
margin-bottom:22px; text-transform:uppercase;
}
.pulse-dot {
width:8px; height:8px; border-radius:50%; background:#22c55e;
animation: pulse 2s ease infinite;
}

.hero-name {
font-size: clamp(42px,9vw,64px);
font-weight:800; letter-spacing:-.035em; line-height:1.05;
margin-bottom:14px;
}
.grad {
background: linear-gradient(110deg, var(–cyan) 0%, #00b8ff 45%, var(–purple) 90%);
-webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
}

.typewriter-line {
font-family:‘Space Mono’,monospace;
font-size:15px; color:var(–muted);
letter-spacing:.04em; margin-bottom:18px;
}
.tw-accent { color:var(–cyan); }
.cursor { animation: blink 1s step-end infinite; color:var(–cyan); }

.hero-sub {
font-size:14.5px; color:#666; max-width:460px;
margin:0 auto; line-height:1.75;
}

/* ── STATS ── */
.stats-grid {
display:grid; grid-template-columns:repeat(4,1fr);
gap:10px; margin-bottom:32px;
}
.stat {
text-align:center; padding:18px 8px; border-radius:16px;
background:var(–surface); border:1px solid var(–border);
transition:.3s;
}
.stat:hover { border-color:rgba(94,240,240,.25); background:rgba(94,240,240,.04); transform:translateY(-2px); }
.stat-val {
font-family:‘Space Mono’,monospace; font-size:24px; font-weight:700;
background:linear-gradient(135deg,var(–cyan),var(–purple));
-webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
display:block; margin-bottom:4px;
}
.stat-lbl { font-size:10px; color:var(–muted); letter-spacing:.07em; text-transform:uppercase; }

/* ── CARDS ── */
.card {
background:var(–surface); border:1px solid var(–border);
border-radius:22px; padding:30px; margin-bottom:18px;
transition:.3s;
}
.card:hover { border-color:rgba(94,240,240,.2); background:rgba(94,240,240,.025); }

.card-title {
display:flex; align-items:center; gap:10px;
font-size:11px; font-weight:700; letter-spacing:.1em;
text-transform:uppercase; color:var(–cyan); margin-bottom:22px;
}
.card-title .ico { font-size:17px; }

/* ── ABOUT ── */
.about-list { display:flex; flex-direction:column; gap:13px; }
.about-item { display:flex; align-items:flex-start; gap:12px; }
.about-icon { font-size:15px; margin-top:2px; flex-shrink:0; }
.about-text { font-size:14px; color:#999; line-height:1.65; }

/* ── SKILLS ── */
.tabs { display:flex; flex-wrap:wrap; gap:8px; margin-bottom:20px; }
.tab {
padding:7px 18px; border-radius:100px;
font-size:12px; font-weight:600; letter-spacing:.03em;
border:1px solid transparent; cursor:pointer;
font-family:‘Sora’,sans-serif; transition:.2s;
}
.tab.on  { background:rgba(94,240,240,.1); border-color:rgba(94,240,240,.4); color:var(–cyan); }
.tab.off { background:transparent; color:var(–muted); }
.tab.off:hover { color:#ccc; border-color:rgba(255,255,255,.15); }

.tag-grid { display:flex; flex-wrap:wrap; gap:8px; }
.tag {
padding:6px 15px; border-radius:100px;
font-size:12.5px; font-weight:500; letter-spacing:.02em;
border:1px solid rgba(94,240,240,.2);
background:rgba(94,240,240,.05); color:var(–cyan);
transition:.2s; cursor:default;
}
.tag:hover { background:rgba(94,240,240,.13); border-color:rgba(94,240,240,.5); transform:scale(1.05); }

/* ── SOCIALS ── */
.social-list { display:flex; flex-direction:column; gap:10px; }
.social-link {
display:flex; align-items:center; gap:14px;
padding:13px 20px; border-radius:16px;
background:rgba(255,255,255,.03); border:1px solid rgba(255,255,255,.08);
color:#bbb; text-decoration:none; font-size:14px; font-weight:500;
transition:.25s;
}
.social-link:hover { background:rgba(255,255,255,.07); border-color:rgba(255,255,255,.2); color:#fff; transform:translateX(4px); }
.social-link svg { flex-shrink:0; }
.social-arrow { margin-left:auto; font-size:12px; color:var(–muted); }

/* ── QUOTE ── */
.quote-block {
border-left:2px solid rgba(94,240,240,.3);
padding-left:22px; font-style:italic;
color:#777; line-height:1.85; font-size:14.5px;
}
.q-word-1 { color:var(–cyan); font-style:normal; font-weight:600; }
.q-word-2 { color:var(–purple); font-style:normal; font-weight:600; }
.q-word-3 { color:var(–pink); font-style:normal; font-weight:600; }

/* ── FOOTER ── */
.divider {
height:1px;
background:linear-gradient(90deg,transparent,rgba(255,255,255,.07),transparent);
margin:36px 0;
}
.footer-text {
text-align:center; font-family:‘Space Mono’,monospace;
font-size:11px; color:#333; letter-spacing:.12em;
}
.footer-dot { color:var(–cyan); }

/* ── RESPONSIVE ── */
@media(max-width:520px){
.stats-grid { grid-template-columns:repeat(2,1fr); }
.hero-name  { font-size:38px; }
}
</style>

</head>
<body>

<div class="bg-orb orb-1"></div>
<div class="bg-orb orb-2"></div>
<div class="bg-orb orb-3"></div>
<div class="noise"></div>

<div class="wrap">

  <!-- HERO -->

  <div class="hero fade d1">
    <div class="avatar-wrap">
      <div class="avatar-ring">
        <div class="avatar-inner">
          <div class="avatar-emoji">🧑‍💻</div>
        </div>
      </div>
    </div>

```
<div><span class="status-badge"><span class="pulse-dot"></span>Available for Opportunities</span></div>

<h1 class="hero-name">
  Rajendra <span class="grad">Bist</span>
</h1>

<div class="typewriter-line">
  ~/ <span class="tw-accent" id="tw"></span><span class="cursor">|</span>
</div>

<p class="hero-sub">
  Crafting performant, scalable web applications with clean architecture.<br/>
  Turning complex ideas into elegant, production-ready solutions.
</p>
```

  </div>

  <!-- STATS -->

  <div class="stats-grid fade d2">
    <div class="stat"><span class="stat-val">10+</span><span class="stat-lbl">Projects Built</span></div>
    <div class="stat"><span class="stat-val">8+</span><span class="stat-lbl">Technologies</span></div>
    <div class="stat"><span class="stat-val">500+</span><span class="stat-lbl">Commits</span></div>
    <div class="stat"><span class="stat-val">∞</span><span class="stat-lbl">Coffee Cups</span></div>
  </div>

  <!-- ABOUT -->

  <div class="card fade d3">
    <div class="card-title"><span class="ico">🚀</span> About Me</div>
    <div class="about-list">
      <div class="about-item"><span class="about-icon">🔭</span><span class="about-text">Building real-world full-stack applications end-to-end with modern tools</span></div>
      <div class="about-item"><span class="about-icon">🌱</span><span class="about-text">Mastering the JavaScript ecosystem — React, Node.js, and beyond</span></div>
      <div class="about-item"><span class="about-icon">🧠</span><span class="about-text">Passionate about clean architecture, scalable system design, and DRY code</span></div>
      <div class="about-item"><span class="about-icon">🎯</span><span class="about-text">Goal: shipping production-ready products that solve real problems</span></div>
    </div>
  </div>

  <!-- SKILLS -->

  <div class="card fade d4">
    <div class="card-title"><span class="ico">🛠️</span> Tech Stack</div>
    <div class="tabs" id="tabs">
      <button class="tab on" data-cat="Frontend"  onclick="switchTab(this)">Frontend</button>
      <button class="tab off" data-cat="Backend"  onclick="switchTab(this)">Backend</button>
      <button class="tab off" data-cat="Database" onclick="switchTab(this)">Database</button>
      <button class="tab off" data-cat="Tools"    onclick="switchTab(this)">Tools</button>
    </div>
    <div class="tag-grid" id="tags"></div>
  </div>

  <!-- CONNECT -->

  <div class="card fade d5">
    <div class="card-title"><span class="ico">🌐</span> Connect With Me</div>
    <div class="social-list">

```
  <a href="https://www.linkedin.com/in/rajendra-bist-169926370" target="_blank" class="social-link">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="#0A66C2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
    LinkedIn
    <span class="social-arrow">↗</span>
  </a>

  <a href="https://www.instagram.com/rajendrabist07" target="_blank" class="social-link">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="#E4405F"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
    Instagram
    <span class="social-arrow">↗</span>
  </a>

  <a href="https://www.facebook.com/share/1FXc1WLiqS/" target="_blank" class="social-link">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="#1877F2"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
    Facebook
    <span class="social-arrow">↗</span>
  </a>

</div>
```

  </div>

  <!-- PHILOSOPHY -->

  <div class="card fade d6">
    <div class="card-title"><span class="ico">💭</span> Philosophy</div>
    <div class="quote-block">
      Code is not just written —<br/>
      it is <span class="q-word-1">designed</span>,
      <span class="q-word-2">structured</span>, and
      <span class="q-word-3">evolved</span>.
    </div>
  </div>

  <!-- FOOTER -->

  <div class="fade d6">
    <div class="divider"></div>
    <p class="footer-text">
      <span class="footer-dot">⭐</span>
      BUILDING <span class="footer-dot">·</span>
      LEARNING <span class="footer-dot">·</span>
      IMPROVING <span class="footer-dot">·</span>
      EVERY DAY
    </p>
  </div>

</div><!-- /wrap -->

<script>
// ── Skills data ──
const skills = {
  Frontend: ['HTML5','CSS3','JavaScript','React','Tailwind CSS'],
  Backend:  ['Node.js','Express.js'],
  Database: ['MongoDB'],
  Tools:    ['Git','GitHub','VS Code','Figma'],
};

function renderTags(cat) {
  const el = document.getElementById('tags');
  el.innerHTML = skills[cat]
    .map(s => `<span class="tag">${s}</span>`)
    .join('');
}

function switchTab(btn) {
  document.querySelectorAll('.tab').forEach(t => { t.className = 'tab off'; });
  btn.className = 'tab on';
  renderTags(btn.dataset.cat);
}

renderTags('Frontend');

// ── Typewriter ──
const words = ['full-stack-dev','mern-specialist','ui-architect','problem-solver'];
let wi = 0, ci = 0, deleting = false;
const twEl = document.getElementById('tw');

function typeLoop() {
  const word = words[wi];
  if (!deleting) {
    twEl.textContent = word.slice(0, ++ci);
    if (ci === word.length) { deleting = true; setTimeout(typeLoop, 1600); return; }
    setTimeout(typeLoop, 80);
  } else {
    twEl.textContent = word.slice(0, --ci);
    if (ci === 0) { deleting = false; wi = (wi + 1) % words.length; }
    setTimeout(typeLoop, deleting ? 45 : 80);
  }
}
typeLoop();
</script>

</body>
</html>