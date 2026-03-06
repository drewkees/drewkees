<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Andrew Baldonado — Hero Banner</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #080c10;
    --grid: #0d1520;
    --cyan: #00f5d4;
    --blue: #0090ff;
    --violet: #7c3aed;
    --white: #e8f0fe;
    --dim: #4a6480;
    --glow-cyan: 0 0 8px #00f5d4aa, 0 0 24px #00f5d444;
    --glow-blue: 0 0 8px #0090ffaa, 0 0 24px #0090ff44;
  }

  html, body {
    background: var(--bg);
    font-family: 'Share Tech Mono', monospace;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  /* ── grid bg ── */
  .bg-grid {
    position: fixed; inset: 0; z-index: 0;
    background-image:
      linear-gradient(var(--grid) 1px, transparent 1px),
      linear-gradient(90deg, var(--grid) 1px, transparent 1px);
    background-size: 44px 44px;
    mask-image: radial-gradient(ellipse 80% 70% at 50% 50%, black 40%, transparent 100%);
  }

  /* ── scanlines ── */
  .scanlines {
    position: fixed; inset: 0; z-index: 1; pointer-events: none;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 3px,
      rgba(0,0,0,0.08) 3px,
      rgba(0,0,0,0.08) 4px
    );
  }

  /* ── aurora blobs ── */
  .aurora {
    position: fixed; inset: 0; z-index: 0; overflow: hidden;
  }
  .aurora span {
    position: absolute; border-radius: 50%; filter: blur(90px); opacity: 0.18;
  }
  .aurora .a1 { width: 500px; height: 500px; background: var(--cyan); top: -100px; left: -100px; animation: drift1 14s ease-in-out infinite alternate; }
  .aurora .a2 { width: 400px; height: 400px; background: var(--blue); bottom: -100px; right: -80px; animation: drift2 11s ease-in-out infinite alternate; }
  .aurora .a3 { width: 300px; height: 300px; background: var(--violet); top: 30%; left: 40%; animation: drift3 17s ease-in-out infinite alternate; }

  @keyframes drift1 { from { transform: translate(0,0) scale(1); } to { transform: translate(80px,60px) scale(1.1); } }
  @keyframes drift2 { from { transform: translate(0,0) scale(1); } to { transform: translate(-60px,-40px) scale(1.15); } }
  @keyframes drift3 { from { transform: translate(0,0) scale(1); } to { transform: translate(40px,-60px) scale(0.9); } }

  /* ── card ── */
  .card {
    position: relative; z-index: 10;
    width: min(720px, 95vw);
    border: 1px solid rgba(0,245,212,0.18);
    border-radius: 4px;
    background: rgba(8,14,22,0.82);
    backdrop-filter: blur(16px);
    padding: 48px 52px 44px;
    box-shadow: 0 0 0 1px rgba(0,245,212,0.06), 0 32px 80px rgba(0,0,0,0.6), inset 0 1px 0 rgba(255,255,255,0.04);
    animation: fadeUp 0.9s cubic-bezier(0.22,1,0.36,1) both;
  }
  @keyframes fadeUp { from { opacity:0; transform:translateY(28px); } to { opacity:1; transform:translateY(0); } }

  /* corner decorators */
  .card::before, .card::after {
    content:''; position:absolute; width:18px; height:18px;
    border-color: var(--cyan); border-style: solid; opacity: 0.7;
  }
  .card::before { top:-1px; left:-1px; border-width: 2px 0 0 2px; }
  .card::after  { bottom:-1px; right:-1px; border-width: 0 2px 2px 0; }

  /* ── terminal bar ── */
  .terminal-bar {
    display: flex; align-items: center; gap: 7px;
    margin-bottom: 32px;
    padding-bottom: 16px;
    border-bottom: 1px solid rgba(0,245,212,0.1);
  }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot.r { background: #ff5f57; }
  .dot.y { background: #ffbd2e; }
  .dot.g { background: #28c840; }
  .terminal-label {
    margin-left: 8px; font-size: 11px; color: var(--dim); letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  /* ── prompt line ── */
  .prompt { color: var(--dim); font-size: 13px; margin-bottom: 10px; }
  .prompt .cmd { color: var(--cyan); text-shadow: var(--glow-cyan); }

  /* ── name ── */
  .name-row {
    display: flex; align-items: baseline; gap: 14px;
    margin: 6px 0 4px;
  }
  .name-prefix { color: var(--cyan); font-size: 22px; text-shadow: var(--glow-cyan); }
  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(32px, 6vw, 54px);
    font-weight: 800;
    color: var(--white);
    letter-spacing: -0.02em;
    line-height: 1;
  }

  /* ── typewriter line ── */
  .typewriter-wrap {
    min-height: 32px; margin: 18px 0 26px;
    display: flex; align-items: center; gap: 8px;
  }
  .tw-label { color: var(--blue); font-size: 14px; text-shadow: var(--glow-blue); }
  .typewriter {
    font-size: clamp(16px, 2.5vw, 22px);
    color: var(--cyan);
    text-shadow: var(--glow-cyan);
    letter-spacing: 0.02em;
  }
  .cursor {
    display: inline-block; width: 2px; height: 1.15em;
    background: var(--cyan); vertical-align: middle;
    box-shadow: var(--glow-cyan);
    animation: blink 0.75s step-end infinite;
    margin-left: 2px;
  }
  @keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0;} }

  /* ── tags ── */
  .tags { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 28px; }
  .tag {
    font-size: 11px; letter-spacing: 0.1em; text-transform: uppercase;
    padding: 4px 12px; border-radius: 2px;
    border: 1px solid rgba(0,245,212,0.22);
    color: var(--dim);
    background: rgba(0,245,212,0.04);
    transition: all 0.25s;
  }
  .tag:hover {
    color: var(--cyan); border-color: var(--cyan);
    background: rgba(0,245,212,0.08);
    box-shadow: var(--glow-cyan);
    cursor: default;
  }

  /* ── divider ── */
  .divider {
    height: 1px; margin: 4px 0 24px;
    background: linear-gradient(90deg, var(--cyan) 0%, var(--blue) 40%, transparent 100%);
    opacity: 0.25;
  }

  /* ── stat row ── */
  .stats { display: flex; gap: 28px; flex-wrap: wrap; }
  .stat { display: flex; flex-direction: column; gap: 3px; }
  .stat-label { font-size: 10px; color: var(--dim); letter-spacing: 0.12em; text-transform: uppercase; }
  .stat-value {
    font-size: 20px; font-family: 'Syne', sans-serif; font-weight: 700;
    color: var(--white);
  }
  .stat-value span { color: var(--cyan); text-shadow: var(--glow-cyan); }

  /* ── signal line ── */
  .signal-line {
    margin-top: 28px; padding-top: 20px;
    border-top: 1px solid rgba(0,245,212,0.08);
    display: flex; align-items: center; gap: 10px;
    font-size: 12px; color: var(--dim);
  }
  .pulse {
    width: 8px; height: 8px; border-radius: 50%;
    background: var(--cyan); box-shadow: var(--glow-cyan);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse {
    0%,100% { transform: scale(1); opacity:1; }
    50% { transform: scale(1.4); opacity:0.6; }
  }
  .signal-line .loc { color: var(--cyan); }

  /* ── boot sequence ── */
  .boot { margin-bottom: 20px; }
  .boot-line {
    font-size: 11px; color: var(--dim); opacity: 0;
    animation: bootIn 0.4s ease forwards;
    letter-spacing: 0.05em;
  }
  .boot-line .ok  { color: #28c840; margin-right: 8px; }
  .boot-line .warn{ color: #ffbd2e; margin-right: 8px; }
  .boot-line:nth-child(1) { animation-delay: 0.1s; }
  .boot-line:nth-child(2) { animation-delay: 0.4s; }
  .boot-line:nth-child(3) { animation-delay: 0.7s; }
  @keyframes bootIn { from{opacity:0;transform:translateX(-8px);} to{opacity:1;transform:none;} }

</style>
</head>
<body>

<div class="aurora">
  <span class="a1"></span>
  <span class="a2"></span>
  <span class="a3"></span>
</div>
<div class="bg-grid"></div>
<div class="scanlines"></div>

<div class="card">

  <!-- terminal bar -->
  <div class="terminal-bar">
    <div class="dot r"></div>
    <div class="dot y"></div>
    <div class="dot g"></div>
    <span class="terminal-label">andrew@dev ~ portfolio</span>
  </div>

  <!-- boot lines -->
  <div class="boot">
    <div class="boot-line"><span class="ok">✔</span> Systems online · Stack loaded</div>
    <div class="boot-line"><span class="ok">✔</span> Full-stack + Embedded modules initialised</div>
    <div class="boot-line"><span class="warn">▶</span> Launching developer profile…</div>
  </div>

  <!-- prompt -->
  <div class="prompt">
    <span class="cmd">whoami</span>
  </div>

  <!-- name -->
  <div class="name-row">
    <span class="name-prefix">//</span>
    <span class="name">Andrew Baldonado</span>
  </div>

  <!-- typewriter -->
  <div class="typewriter-wrap">
    <span class="tw-label">role →</span>
    <span class="typewriter" id="tw"></span><span class="cursor"></span>
  </div>

  <!-- tags -->
  <div class="tags">
    <span class="tag">VB.NET</span>
    <span class="tag">React</span>
    <span class="tag">TypeScript</span>
    <span class="tag">MySQL</span>
    <span class="tag">Arduino</span>
    <span class="tag">Raspberry Pi</span>
    <span class="tag">C++</span>
    <span class="tag">Docker</span>
    <span class="tag">Linux</span>
  </div>

  <div class="divider"></div>

  <!-- stats -->
  <div class="stats">
    <div class="stat">
      <span class="stat-label">Focus</span>
      <span class="stat-value"><span>Full-Stack</span> Dev</span>
    </div>
    <div class="stat">
      <span class="stat-label">Specialty</span>
      <span class="stat-value"><span>SW</span> + HW</span>
    </div>
    <div class="stat">
      <span class="stat-label">Domain</span>
      <span class="stat-value"><span>AI</span> Automation</span>
    </div>
  </div>

  <!-- signal -->
  <div class="signal-line">
    <div class="pulse"></div>
    <span>Available for projects ·</span>
    <span class="loc">baldonado0514@gmail.com</span>
  </div>

</div>

<script>
  const phrases = [
    "Software Developer",
    "AI Automation Specialist",
    "Full-Stack Engineer",
    "Embedded Systems Builder",
    "Bridging Software & Hardware",
  ];

  let pi = 0, ci = 0, deleting = false, paused = false;

  function type() {
    if (paused) { setTimeout(type, 1400); paused = false; return; }
    const el = document.getElementById('tw');
    const word = phrases[pi];
    if (!deleting) {
      el.textContent = word.slice(0, ++ci);
      if (ci === word.length) { deleting = true; paused = true; setTimeout(type, 60); return; }
      setTimeout(type, 72);
    } else {
      el.textContent = word.slice(0, --ci);
      if (ci === 0) {
        deleting = false;
        pi = (pi + 1) % phrases.length;
        setTimeout(type, 380);
        return;
      }
      setTimeout(type, 38);
    }
  }
  setTimeout(type, 1200);
</script>
</body>
</html>
