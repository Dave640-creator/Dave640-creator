<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub Profile README</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600&display=swap" rel="stylesheet">
<style>
  :root {
    --neon-cyan: #00f5ff;
    --neon-purple: #bf00ff;
    --neon-pink: #ff006e;
    --neon-green: #39ff14;
    --dark-bg: #020010;
    --card-bg: rgba(10, 0, 40, 0.85);
    --glass: rgba(0, 245, 255, 0.05);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--dark-bg);
    color: #e0e0ff;
    font-family: 'Rajdhani', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ── STARFIELD ── */
  #stars-canvas {
    position: fixed;
    inset: 0;
    z-index: 0;
    pointer-events: none;
  }

  /* ── GRID FLOOR ── */
  .grid-floor {
    position: fixed;
    bottom: 0; left: 0; right: 0;
    height: 40vh;
    background:
      linear-gradient(transparent 0%, rgba(0,245,255,0.04) 100%),
      repeating-linear-gradient(90deg, rgba(0,245,255,0.08) 0 1px, transparent 1px 60px),
      repeating-linear-gradient(0deg,  rgba(0,245,255,0.08) 0 1px, transparent 1px 60px);
    perspective: 600px;
    transform: rotateX(60deg);
    transform-origin: bottom;
    z-index: 0;
    animation: gridPulse 4s ease-in-out infinite alternate;
  }
  @keyframes gridPulse {
    from { opacity: .4; }
    to   { opacity: .9; }
  }

  /* ── WRAPPER ── */
  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 20px 80px;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 60px 0 40px;
    animation: fadeUp .8s ease both;
  }
  @keyframes fadeUp {
    from { opacity:0; transform:translateY(30px); }
    to   { opacity:1; transform:translateY(0);    }
  }

  .avatar-ring {
    display: inline-block;
    position: relative;
    margin-bottom: 24px;
  }
  .avatar-ring::before, .avatar-ring::after {
    content: '';
    position: absolute;
    inset: -6px;
    border-radius: 50%;
    border: 2px solid transparent;
    animation: spinRing 3s linear infinite;
  }
  .avatar-ring::before {
    border-top-color: var(--neon-cyan);
    border-right-color: var(--neon-purple);
  }
  .avatar-ring::after {
    border-bottom-color: var(--neon-pink);
    border-left-color: var(--neon-green);
    animation-direction: reverse;
    animation-duration: 2s;
    inset: -14px;
  }
  @keyframes spinRing {
    to { transform: rotate(360deg); }
  }

  .avatar {
    width: 110px; height: 110px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--neon-purple), var(--neon-cyan));
    display: flex; align-items: center; justify-content: center;
    font-size: 48px;
    position: relative;
    z-index: 1;
    box-shadow: 0 0 30px rgba(0,245,255,.4), 0 0 60px rgba(191,0,255,.3);
  }

  .glitch-name {
    font-family: 'Orbitron', monospace;
    font-size: clamp(28px, 6vw, 48px);
    font-weight: 900;
    letter-spacing: .05em;
    position: relative;
    display: inline-block;
    color: #fff;
    text-shadow: 0 0 20px var(--neon-cyan);
    animation: glitchAnim 6s infinite;
  }
  @keyframes glitchAnim {
    0%,94%,100% { text-shadow: 0 0 20px var(--neon-cyan); transform: none; }
    95% { text-shadow: -3px 0 var(--neon-pink), 3px 0 var(--neon-cyan); transform: skewX(-2deg); }
    97% { text-shadow: 3px 0 var(--neon-purple), -3px 0 var(--neon-green); transform: skewX(2deg); }
  }

  .subtitle {
    font-size: 16px;
    letter-spacing: .25em;
    color: var(--neon-cyan);
    opacity: .8;
    margin-top: 8px;
    text-transform: uppercase;
  }

  /* ── TYPING BADGE ── */
  .typing-wrap {
    margin: 18px auto 0;
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: var(--glass);
    border: 1px solid rgba(0,245,255,.2);
    border-radius: 40px;
    padding: 8px 20px;
    backdrop-filter: blur(8px);
  }
  .dot-pulse { width: 8px; height: 8px; border-radius: 50%; background: var(--neon-green); animation: dotPulse 1.2s ease infinite; }
  @keyframes dotPulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:.3;transform:scale(.6)} }
  #typed-text { font-size: 14px; letter-spacing: .08em; color: #cdd; min-width: 220px; }
  .cursor { display: inline-block; width: 2px; height: 14px; background: var(--neon-cyan); animation: blink .7s step-end infinite; vertical-align: middle; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── SECTION LABEL ── */
  .section-label {
    font-family: 'Orbitron', monospace;
    font-size: 11px;
    letter-spacing: .3em;
    color: var(--neon-cyan);
    text-transform: uppercase;
    margin-bottom: 20px;
    padding-left: 4px;
    opacity: .7;
    animation: fadeUp .8s ease both;
    animation-delay: .2s;
  }

  /* ── CARD ── */
  .card {
    background: var(--card-bg);
    border: 1px solid rgba(0,245,255,.15);
    border-radius: 16px;
    padding: 28px;
    margin-bottom: 24px;
    backdrop-filter: blur(12px);
    position: relative;
    overflow: hidden;
    animation: fadeUp .8s ease both;
    transition: transform .3s, box-shadow .3s;
  }
  .card:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 40px rgba(0,245,255,.15), 0 0 0 1px rgba(0,245,255,.25);
  }
  .card::before {
    content: '';
    position: absolute;
    top: 0; left: -100%;
    width: 60%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(0,245,255,.04), transparent);
    animation: shimmer 4s ease infinite;
  }
  @keyframes shimmer { to { left: 200%; } }

  .card-title {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    letter-spacing: .2em;
    color: var(--neon-cyan);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .card-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(0,245,255,.4), transparent);
  }

  /* ── ABOUT ── */
  .about-text {
    font-size: 15px;
    line-height: 1.8;
    color: #b0b8d0;
  }
  .about-text span { color: var(--neon-cyan); font-weight: 600; }

  /* ── SKILLS GRID ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
    gap: 12px;
  }
  .skill-chip {
    background: rgba(0,245,255,.06);
    border: 1px solid rgba(0,245,255,.18);
    border-radius: 10px;
    padding: 12px 8px;
    text-align: center;
    font-size: 11px;
    letter-spacing: .05em;
    color: #a0b8d0;
    cursor: default;
    transition: all .25s;
    position: relative;
    overflow: hidden;
  }
  .skill-chip:hover {
    background: rgba(0,245,255,.12);
    border-color: var(--neon-cyan);
    color: #fff;
    transform: scale(1.06) translateY(-2px);
    box-shadow: 0 4px 20px rgba(0,245,255,.2);
  }
  .skill-chip .icon { font-size: 22px; display: block; margin-bottom: 5px; }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }
  .stat-box {
    text-align: center;
    padding: 20px 10px;
    background: rgba(191,0,255,.06);
    border: 1px solid rgba(191,0,255,.18);
    border-radius: 12px;
    transition: all .25s;
  }
  .stat-box:hover {
    background: rgba(191,0,255,.12);
    border-color: var(--neon-purple);
    transform: translateY(-3px);
    box-shadow: 0 6px 24px rgba(191,0,255,.2);
  }
  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 28px;
    font-weight: 900;
    background: linear-gradient(135deg, var(--neon-cyan), var(--neon-purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    counter-reset: num;
    animation: countUp 2s ease both;
  }
  .stat-label { font-size: 11px; letter-spacing: .15em; color: #778; margin-top: 4px; text-transform: uppercase; }

  /* ── PROJECTS ── */
  .projects-list { display: flex; flex-direction: column; gap: 14px; }
  .project-item {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 16px 18px;
    background: rgba(255,0,110,.04);
    border: 1px solid rgba(255,0,110,.12);
    border-radius: 12px;
    cursor: pointer;
    transition: all .25s;
  }
  .project-item:hover {
    background: rgba(255,0,110,.1);
    border-color: var(--neon-pink);
    transform: translateX(6px);
    box-shadow: -4px 0 20px rgba(255,0,110,.15);
  }
  .project-icon {
    width: 40px; height: 40px;
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    background: rgba(255,0,110,.1);
    flex-shrink: 0;
  }
  .project-name { font-weight: 600; font-size: 14px; color: #dde; }
  .project-desc { font-size: 12px; color: #778; margin-top: 2px; }
  .project-lang {
    margin-left: auto;
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 20px;
    background: rgba(255,0,110,.12);
    color: var(--neon-pink);
    border: 1px solid rgba(255,0,110,.25);
    white-space: nowrap;
  }

  /* ── STREAK BAR ── */
  .streak-bar-wrap { margin-top: 8px; }
  .streak-label { display: flex; justify-content: space-between; font-size: 12px; color: #668; margin-bottom: 6px; }
  .streak-track {
    height: 8px;
    background: rgba(255,255,255,.05);
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 14px;
  }
  .streak-fill {
    height: 100%;
    border-radius: 8px;
    background: linear-gradient(90deg, var(--neon-cyan), var(--neon-purple));
    width: 0;
    animation: fillBar 1.5s ease forwards;
    box-shadow: 0 0 10px rgba(0,245,255,.5);
  }
  @keyframes fillBar { to { width: var(--w); } }

  /* ── CONNECT ── */
  .connect-row {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
  }
  .connect-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 22px;
    border-radius: 40px;
    border: 1px solid;
    font-family: 'Rajdhani', sans-serif;
    font-size: 13px;
    letter-spacing: .1em;
    text-decoration: none;
    cursor: pointer;
    transition: all .25s;
    background: transparent;
    font-weight: 600;
  }
  .btn-github  { border-color: rgba(200,200,200,.3); color: #ccc; }
  .btn-twitter { border-color: rgba(29,161,242,.3);  color: #1da1f2; }
  .btn-linkedin{ border-color: rgba(0,119,181,.3);   color: #0077b5; }
  .btn-mail    { border-color: rgba(255,0,110,.3);   color: var(--neon-pink); }
  .connect-btn:hover {
    transform: scale(1.06) translateY(-2px);
    box-shadow: 0 6px 24px rgba(0,0,0,.3);
    filter: brightness(1.3);
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    font-size: 11px;
    letter-spacing: .2em;
    color: rgba(0,245,255,.3);
    padding-top: 20px;
    text-transform: uppercase;
    animation: fadeUp .8s ease both;
    animation-delay: .6s;
  }

  /* ── ANIMATION DELAYS ── */
  .card:nth-child(1) { animation-delay: .1s; }
  .card:nth-child(2) { animation-delay: .2s; }
  .card:nth-child(3) { animation-delay: .3s; }
  .card:nth-child(4) { animation-delay: .4s; }
  .card:nth-child(5) { animation-delay: .5s; }
</style>
</head>
<body>

<canvas id="stars-canvas"></canvas>
<div class="grid-floor"></div>

<div class="wrapper">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-ring">
      <div class="avatar">👨‍💻</div>
    </div>
    <div class="glitch-name">YOUR NAME</div>
    <div class="subtitle">Full Stack Developer · AI Enthusiast</div>
    <div class="typing-wrap">
      <div class="dot-pulse"></div>
      <span id="typed-text"></span><span class="cursor"></span>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section-label">// about.me</div>
  <div class="card">
    <div class="card-title">⚡ WHO AM I</div>
    <p class="about-text">
      Hi! I'm <span>@YourUsername</span>, a passionate developer who loves building
      <span>elegant solutions</span> to complex problems. I thrive at the intersection of
      <span>creativity & code</span> — turning wild ideas into real, working products.
      Currently exploring the world of <span>AI & Machine Learning</span>. 🚀
    </p>
  </div>

  <!-- SKILLS -->
  <div class="section-label">// tech.stack</div>
  <div class="card">
    <div class="card-title">🛠 SKILLS & TOOLS</div>
    <div class="skills-grid">
      <div class="skill-chip"><span class="icon">🐍</span>Python</div>
      <div class="skill-chip"><span class="icon">⚛️</span>React</div>
      <div class="skill-chip"><span class="icon">🟨</span>JavaScript</div>
      <div class="skill-chip"><span class="icon">🔷</span>TypeScript</div>
      <div class="skill-chip"><span class="icon">🐳</span>Docker</div>
      <div class="skill-chip"><span class="icon">☁️</span>AWS</div>
      <div class="skill-chip"><span class="icon">🔥</span>Firebase</div>
      <div class="skill-chip"><span class="icon">🗄️</span>SQL</div>
      <div class="skill-chip"><span class="icon">🍃</span>MongoDB</div>
      <div class="skill-chip"><span class="icon">🦀</span>Rust</div>
      <div class="skill-chip"><span class="icon">🤖</span>ML / AI</div>
      <div class="skill-chip"><span class="icon">🐧</span>Linux</div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section-label">// github.stats</div>
  <div class="card">
    <div class="card-title">📊 CONTRIBUTIONS</div>
    <div class="stats-grid">
      <div class="stat-box">
        <div class="stat-num" id="s1">0</div>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-box">
        <div class="stat-num" id="s2">0</div>
        <div class="stat-label">Commits</div>
      </div>
      <div class="stat-box">
        <div class="stat-num" id="s3">0</div>
        <div class="stat-label">Stars Earned</div>
      </div>
    </div>
    <div class="streak-bar-wrap" style="margin-top:24px">
      <div class="streak-label"><span>JavaScript</span><span>65%</span></div>
      <div class="streak-track"><div class="streak-fill" style="--w:65%"></div></div>
      <div class="streak-label"><span>Python</span><span>50%</span></div>
      <div class="streak-track"><div class="streak-fill" style="--w:50%; animation-delay:.2s"></div></div>
      <div class="streak-label"><span>TypeScript</span><span>35%</span></div>
      <div class="streak-track"><div class="streak-fill" style="--w:35%; animation-delay:.4s"></div></div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section-label">// pinned.projects</div>
  <div class="card">
    <div class="card-title">🚀 FEATURED PROJECTS</div>
    <div class="projects-list">
      <div class="project-item">
        <div class="project-icon">🤖</div>
        <div>
          <div class="project-name">AI Chatbot Engine</div>
          <div class="project-desc">Offline LLM-powered chatbot using Ollama + Python</div>
        </div>
        <div class="project-lang">Python</div>
      </div>
      <div class="project-item">
        <div class="project-icon">🌐</div>
        <div>
          <div class="project-name">Portfolio Website</div>
          <div class="project-desc">3D animated personal portfolio with Three.js</div>
        </div>
        <div class="project-lang">React</div>
      </div>
      <div class="project-item">
        <div class="project-icon">📊</div>
        <div>
          <div class="project-name">Data Dashboard</div>
          <div class="project-desc">Real-time analytics dashboard with D3.js</div>
        </div>
        <div class="project-lang">TypeScript</div>
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section-label">// let's.connect</div>
  <div class="card">
    <div class="card-title">🌐 FIND ME HERE</div>
    <div class="connect-row">
      <a class="connect-btn btn-github"  href="#">⚫ GitHub</a>
      <a class="connect-btn btn-twitter" href="#">🐦 Twitter</a>
      <a class="connect-btn btn-linkedin"href="#">💼 LinkedIn</a>
      <a class="connect-btn btn-mail"    href="#">✉️ Email</a>
    </div>
  </div>

  <div class="footer">⚡ Built with passion · Updated 2026 · YourUsername ⚡</div>
</div>

<script>
/* ── STARFIELD ── */
const canvas = document.getElementById('stars-canvas');
const ctx = canvas.getContext('2d');
let stars = [];
function resize() { canvas.width = innerWidth; canvas.height = innerHeight; }
resize(); window.addEventListener('resize', resize);
for (let i = 0; i < 200; i++) stars.push({ x: Math.random(), y: Math.random(), r: Math.random() * 1.5 + .2, speed: Math.random() * .0002 + .00005, opacity: Math.random() });
function drawStars() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  stars.forEach(s => {
    s.y += s.speed; if (s.y > 1) s.y = 0;
    ctx.beginPath();
    ctx.arc(s.x * canvas.width, s.y * canvas.height, s.r, 0, Math.PI*2);
    ctx.fillStyle = `rgba(180,200,255,${s.opacity})`;
    ctx.fill();
  });
  requestAnimationFrame(drawStars);
}
drawStars();

/* ── TYPING ── */
const phrases = [
  'Building the future, one commit at a time.',
  'Always learning. Always shipping. 🚀',
  'Open source lover & coffee addict ☕',
  'Turning ideas into reality with code.',
  'If it works, don\'t touch it. 😅'
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('typed-text');
function type() {
  const phrase = phrases[pi];
  el.textContent = deleting ? phrase.slice(0, --ci) : phrase.slice(0, ++ci);
  if (!deleting && ci === phrase.length) { setTimeout(() => deleting = true, 2000); setTimeout(type, 80); return; }
  if (deleting && ci === 0) { deleting = false; pi = (pi+1) % phrases.length; setTimeout(type, 400); return; }
  setTimeout(type, deleting ? 40 : 70);
}
setTimeout(type, 800);

/* ── COUNT-UP ── */
function countTo(id, target, duration) {
  const el = document.getElementById(id);
  const start = Date.now();
  function update() {
    const progress = Math.min((Date.now() - start) / duration, 1);
    const ease = 1 - Math.pow(1 - progress, 3);
    el.textContent = Math.floor(ease * target);
    if (progress < 1) requestAnimationFrame(update);
  }
  update();
}
const obs = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) { countTo('s1', 42, 1500); countTo('s2', 1247, 1800); countTo('s3', 183, 1600); obs.disconnect(); } });
}, { threshold: .3 });
obs.observe(document.getElementById('s1'));
</script>
</body>
</html>
