<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vishal Mache — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0d0f14;
    --surface: #13161e;
    --surface2: #1a1e2a;
    --border: #242836;
    --accent: #7c6ef2;
    --accent2: #4ecdc4;
    --accent3: #f7c59f;
    --text: #e8eaf0;
    --muted: #7a8099;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(124,110,242,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,110,242,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    max-width: 780px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* BADGE ROW */
  .badge-row {
    display: flex;
    gap: 8px;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 12px;
    border-radius: 50px;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.06em;
  }
  .badge-purple { background: rgba(124,110,242,0.15); color: #a79df5; border: 1px solid rgba(124,110,242,0.3); }
  .badge-teal   { background: rgba(78,205,196,0.12);  color: #5fd6ce; border: 1px solid rgba(78,205,196,0.25); }
  .badge-amber  { background: rgba(247,197,159,0.12); color: #f7c59f; border: 1px solid rgba(247,197,159,0.25); }
  .badge-dot { width: 5px; height: 5px; border-radius: 50%; background: currentColor; }

  /* HEADER */
  .header {
    position: relative;
    padding: 56px 48px;
    border: 1px solid var(--border);
    border-radius: 20px;
    background: var(--surface);
    overflow: hidden;
    margin-bottom: 20px;
  }
  .header::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 320px; height: 320px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(124,110,242,0.18) 0%, transparent 70%);
    pointer-events: none;
  }
  .header::after {
    content: '';
    position: absolute;
    bottom: -60px; left: -40px;
    width: 220px; height: 220px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(78,205,196,0.12) 0%, transparent 70%);
    pointer-events: none;
  }
  .header-tag {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent2);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 18px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .header-tag::before {
    content: '';
    display: inline-block;
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent2);
    box-shadow: 0 0 8px var(--accent2);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }
  .header-name {
    font-size: clamp(36px, 6vw, 58px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #e8eaf0 30%, #7c6ef2 70%, #4ecdc4 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 14px;
  }
  .header-subtitle {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--muted);
    line-height: 1.9;
    max-width: 480px;
  }
  .header-subtitle span { color: var(--accent3); }
  .header-actions {
    display: flex;
    gap: 12px;
    margin-top: 28px;
    flex-wrap: wrap;
  }
  .btn {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.08em;
    padding: 10px 20px;
    border-radius: 8px;
    border: 1px solid;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }
  .btn-primary { background: var(--accent); border-color: var(--accent); color: #fff; }
  .btn-primary:hover { background: #9084f5; border-color: #9084f5; transform: translateY(-1px); }
  .btn-ghost { background: transparent; border-color: var(--border); color: var(--muted); }
  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-1px); }

  /* STATUS STRIP */
  .status-strip {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 20px;
  }
  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px 22px;
    transition: border-color 0.2s, transform 0.2s;
    position: relative;
    overflow: hidden;
  }
  .stat-card:hover { border-color: var(--accent); transform: translateY(-2px); }
  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    border-radius: 0 0 14px 14px;
  }
  .stat-card.c1::after { background: var(--accent); }
  .stat-card.c2::after { background: var(--accent2); }
  .stat-card.c3::after { background: var(--accent3); }
  .stat-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 8px;
  }
  .stat-value { font-size: 20px; font-weight: 800; color: var(--text); line-height: 1; }
  .stat-sub { font-family: 'Space Mono', monospace; font-size: 10px; color: var(--muted); margin-top: 4px; }

  /* SECTION */
  .section {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 32px;
    margin-bottom: 20px;
    transition: border-color 0.2s;
  }
  .section:hover { border-color: rgba(124,110,242,0.3); }
  .section-head {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 24px;
  }
  .section-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); }
  .section-title {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
  }
  .section-line { flex: 1; height: 1px; background: var(--border); }

  /* SKILLS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(88px, 1fr));
    gap: 10px;
  }
  .skill-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    padding: 14px 10px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    transition: all 0.2s;
    cursor: default;
  }
  .skill-item:hover {
    border-color: var(--accent);
    background: rgba(124,110,242,0.08);
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(124,110,242,0.15);
  }
  .skill-icon { font-size: 22px; line-height: 1; }
  .skill-name {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 0.04em;
    text-align: center;
  }

  /* CURRENTLY */
  .currently-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  .current-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 16px 18px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    transition: all 0.2s;
  }
  .current-item:hover { border-color: var(--accent2); }
  .current-icon {
    width: 34px; height: 34px;
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 16px;
    flex-shrink: 0;
  }
  .ci-purple { background: rgba(124,110,242,0.15); }
  .ci-teal   { background: rgba(78,205,196,0.15); }
  .ci-amber  { background: rgba(247,197,159,0.15); }
  .ci-pink   { background: rgba(255,100,130,0.15); }
  .current-label {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 4px;
  }
  .current-value { font-size: 13px; font-weight: 600; color: var(--text); line-height: 1.3; }

  /* CONNECT */
  .connect-row { display: flex; gap: 12px; flex-wrap: wrap; }
  .social-chip {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 18px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 50px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    text-decoration: none;
    transition: all 0.2s;
  }
  .social-chip:hover {
    border-color: var(--accent);
    color: var(--text);
    background: rgba(124,110,242,0.1);
    transform: translateY(-2px);
  }

  /* GITHUB STATS */
  .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .stats-embed {
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    background: var(--surface2);
    padding: 4px;
  }
  .stats-embed img { width: 100%; display: block; border-radius: 9px; }

  /* FOOTER */
  .footer { text-align: center; padding-top: 20px; }
  .footer-text {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--border);
    letter-spacing: 0.12em;
  }

  /* RESPONSIVE */
  @media (max-width: 560px) {
    .status-strip     { grid-template-columns: 1fr 1fr; }
    .currently-grid   { grid-template-columns: 1fr; }
    .stats-grid       { grid-template-columns: 1fr; }
    .header           { padding: 36px 28px; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- BADGES -->
  <div class="badge-row">
    <span class="badge badge-purple"><span class="badge-dot"></span>Available for collabs</span>
    <span class="badge badge-teal"><span class="badge-dot"></span>Open to opportunities</span>
    <span class="badge badge-amber"><span class="badge-dot"></span>Based in India</span>
  </div>

  <!-- HEADER -->
  <div class="header">
    <div class="header-tag">Full-stack developer in progress</div>
    <h1 class="header-name">Vishal Mache</h1>
    <p class="header-subtitle">
      Passionate <span>frontend developer</span> leveling up to full-stack.<br>
      Building things with React, Flutter &amp; Firebase.<br>
      Currently exploring <span>Python</span> &amp; <span>Dart</span>.
    </p>
    <div class="header-actions">
      <a href="mailto:vismac9@gmail.com" class="btn btn-primary">✉ vismac9@gmail.com</a>
      <a href="https://github.com/VishalMache/Screenique" class="btn btn-ghost">⬡ View Screenique</a>
    </div>
  </div>

  <!-- STAT CARDS -->
  <div class="status-strip">
    <div class="stat-card c1">
      <div class="stat-label">Currently Building</div>
      <div class="stat-value">Screenique</div>
      <div class="stat-sub">Active project</div>
    </div>
    <div class="stat-card c2">
      <div class="stat-label">Learning Now</div>
      <div class="stat-value">Python + Dart</div>
      <div class="stat-sub">In progress</div>
    </div>
    <div class="stat-card c3">
      <div class="stat-label">Goal</div>
      <div class="stat-value">Full-Stack</div>
      <div class="stat-sub">Frontend → Fullstack</div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-head">
      <div class="section-dot"></div>
      <div class="section-title">Tech Stack</div>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">
      <div class="skill-item"><div class="skill-icon">⚛️</div><div class="skill-name">React</div></div>
      <div class="skill-item"><div class="skill-icon">🎨</div><div class="skill-name">Tailwind</div></div>
      <div class="skill-item"><div class="skill-icon">🌐</div><div class="skill-name">HTML5</div></div>
      <div class="skill-item"><div class="skill-icon">💅</div><div class="skill-name">CSS3</div></div>
      <div class="skill-item"><div class="skill-icon">📜</div><div class="skill-name">JavaScript</div></div>
      <div class="skill-item"><div class="skill-icon">🐦</div><div class="skill-name">Flutter</div></div>
      <div class="skill-item"><div class="skill-icon">🎯</div><div class="skill-name">Dart</div></div>
      <div class="skill-item"><div class="skill-icon">🔥</div><div class="skill-name">Firebase</div></div>
      <div class="skill-item"><div class="skill-icon">🐍</div><div class="skill-name">Python</div></div>
      <div class="skill-item"><div class="skill-icon">🤖</div><div class="skill-name">Android</div></div>
      <div class="skill-item"><div class="skill-icon">🌿</div><div class="skill-name">Git</div></div>
      <div class="skill-item"><div class="skill-icon">🎭</div><div class="skill-name">Figma</div></div>
    </div>
  </div>

  <!-- CURRENTLY -->
  <div class="section">
    <div class="section-head">
      <div class="section-dot"></div>
      <div class="section-title">Right Now</div>
      <div class="section-line"></div>
    </div>
    <div class="currently-grid">
      <div class="current-item">
        <div class="current-icon ci-purple">🔭</div>
        <div>
          <div class="current-label">Working on</div>
          <div class="current-value">Screenique</div>
        </div>
      </div>
      <div class="current-item">
        <div class="current-icon ci-teal">🌱</div>
        <div>
          <div class="current-label">Learning</div>
          <div class="current-value">Python &amp; Dart</div>
        </div>
      </div>
      <div class="current-item">
        <div class="current-icon ci-amber">🎯</div>
        <div>
          <div class="current-label">Goal</div>
          <div class="current-value">Become Full-Stack Dev</div>
        </div>
      </div>
      <div class="current-item">
        <div class="current-icon ci-pink">📫</div>
        <div>
          <div class="current-label">Reach me at</div>
          <div class="current-value">vismac9@gmail.com</div>
        </div>
      </div>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-head">
      <div class="section-dot"></div>
      <div class="section-title">GitHub Stats</div>
      <div class="section-line"></div>
    </div>
    <div class="stats-grid">
      <div class="stats-embed">
        <img src="https://github-readme-stats.vercel.app/api/top-langs?username=vishalmache&show_icons=true&locale=en&layout=compact&theme=tokyonight&hide_border=true&bg_color=1a1e2a" alt="Top Languages">
      </div>
      <div class="stats-embed">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=vishalmache&theme=tokyonight&hide_border=true&background=1a1e2a" alt="GitHub Streak">
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section">
    <div class="section-head">
      <div class="section-dot"></div>
      <div class="section-title">Connect</div>
      <div class="section-line"></div>
    </div>
    <div class="connect-row">
      <a href="https://twitter.com/machevishal24114" class="social-chip">𝕏 @machevishal24114</a>
      <a href="https://instagram.com/vismac.21" class="social-chip">◈ @vismac.21</a>
      <a href="mailto:vismac9@gmail.com" class="social-chip">✉ vismac9@gmail.com</a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-text">// crafted with ♥ by vishal mache</div>
  </div>

</div>
</body>
</html>
