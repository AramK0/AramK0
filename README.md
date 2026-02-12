<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aram Karim — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Space+Grotesk:wght@300;400;600&family=Bebas+Neue&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0c0f;
    --surface: #0f1318;
    --surface2: #141a22;
    --border: #1e2a36;
    --accent: #6A9FB5;
    --accent2: #4ecdc4;
    --accent3: #e07b39;
    --text: #c8d8e4;
    --text-dim: #5a7385;
    --text-bright: #e8f4fc;
    --green: #3ddc84;
    --red: #e07b39;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(106,159,181,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(106,159,181,0.03) 1px, transparent 1px);
    background-size: 32px 32px;
    pointer-events: none;
    z-index: 0;
  }

  /* Scanline effect */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.04) 2px,
      rgba(0,0,0,0.04) 4px
    );
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ─── HEADER ─── */
  .header {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 0;
    margin-bottom: 24px;
    position: relative;
    overflow: hidden;
  }

  .header::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }

  .terminal-bar {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 16px;
    background: var(--surface2);
    border-bottom: 1px solid var(--border);
    font-size: 11px;
    color: var(--text-dim);
  }

  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }
  .terminal-title { margin-left: auto; font-size: 11px; color: var(--text-dim); }

  .header-body {
    padding: 36px 40px 32px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 24px;
    align-items: start;
  }

  .prompt-line {
    font-size: 11px;
    color: var(--text-dim);
    margin-bottom: 6px;
    letter-spacing: 0.05em;
  }

  .prompt-line span { color: var(--accent); }

  .name-block {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(52px, 8vw, 88px);
    letter-spacing: 0.04em;
    color: var(--text-bright);
    line-height: 0.9;
    margin-bottom: 16px;
  }

  .name-block .accent-char { color: var(--accent); }

  .tagline {
    font-size: 12.5px;
    color: var(--text-dim);
    line-height: 1.7;
    max-width: 480px;
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 300;
    margin-bottom: 20px;
  }

  .tagline strong {
    color: var(--text);
    font-weight: 600;
  }

  .email-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 11.5px;
    color: var(--accent);
    padding: 6px 12px;
    border: 1px solid rgba(106,159,181,0.25);
    background: rgba(106,159,181,0.05);
    letter-spacing: 0.03em;
  }

  .email-badge::before { content: '✉'; font-size: 10px; }

  .status-block {
    text-align: right;
  }

  .status-tag {
    display: inline-block;
    font-size: 9.5px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 4px 10px;
    margin-bottom: 6px;
    border: 1px solid;
  }

  .status-tag.open {
    color: var(--green);
    border-color: rgba(61,220,132,0.3);
    background: rgba(61,220,132,0.05);
  }

  .typing-display {
    font-size: 10.5px;
    color: var(--text-dim);
    line-height: 1.8;
    margin-top: 12px;
    padding: 10px 12px;
    border: 1px solid var(--border);
    background: var(--bg);
    white-space: nowrap;
  }

  .typing-display .cursor {
    display: inline-block;
    width: 7px;
    height: 12px;
    background: var(--accent);
    vertical-align: middle;
    animation: blink 1s step-end infinite;
    margin-left: 2px;
  }

  @keyframes blink { 0%, 100% { opacity: 1 } 50% { opacity: 0 } }

  /* ─── SECTION LABEL ─── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 14px;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-label .num {
    color: var(--text-dim);
    font-size: 9px;
  }

  /* ─── CARDS ─── */
  .card {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 24px 28px;
    margin-bottom: 24px;
    position: relative;
    transition: border-color 0.2s;
  }

  .card:hover { border-color: rgba(106,159,181,0.35); }

  .card::before {
    content: '';
    position: absolute;
    left: 0; top: 8px; bottom: 8px;
    width: 2px;
    background: var(--border);
    transition: background 0.2s;
  }

  .card:hover::before { background: var(--accent); }

  /* ─── ABOUT ─── */
  .about-text {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 13.5px;
    font-weight: 300;
    color: var(--text);
    line-height: 1.75;
    margin-bottom: 14px;
  }

  .quote-block {
    border-left: 2px solid var(--accent);
    padding: 10px 18px;
    background: rgba(106,159,181,0.04);
    font-size: 11.5px;
    color: var(--text-dim);
    font-style: italic;
    margin-top: 16px;
  }

  .quote-block span { color: var(--accent2); font-style: normal; }

  /* ─── PROJECTS ─── */
  .project-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
  }

  @media (max-width: 580px) { .project-grid { grid-template-columns: 1fr; } }

  .project-card {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 20px 22px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s, background 0.2s;
    cursor: default;
  }

  .project-card:hover {
    border-color: rgba(106,159,181,0.4);
    background: var(--surface2);
  }

  .project-card::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    opacity: 0;
    transition: opacity 0.2s;
  }

  .project-card:hover::after { opacity: 1; }

  .project-num {
    font-size: 9px;
    color: var(--text-dim);
    letter-spacing: 0.1em;
    margin-bottom: 8px;
  }

  .project-name {
    font-size: 13px;
    font-weight: 500;
    color: var(--text-bright);
    margin-bottom: 8px;
    letter-spacing: 0.02em;
  }

  .project-name a { color: inherit; text-decoration: none; }
  .project-name a:hover { color: var(--accent2); }
  .project-name a::after { content: ' ↗'; font-size: 10px; opacity: 0.6; }

  .project-desc {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 11.5px;
    font-weight: 300;
    color: var(--text-dim);
    line-height: 1.65;
    margin-bottom: 14px;
  }

  .tech-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
  }

  .pill {
    font-size: 9px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 3px 8px;
    border: 1px solid var(--border);
    color: var(--text-dim);
    background: var(--bg);
  }

  .pill.highlight {
    border-color: rgba(106,159,181,0.3);
    color: var(--accent);
    background: rgba(106,159,181,0.06);
  }

  /* ─── STACK ─── */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
    margin-bottom: 24px;
  }

  @media (max-width: 580px) { .stack-grid { grid-template-columns: 1fr; } }

  .stack-category {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 18px 18px 16px;
  }

  .stack-cat-label {
    font-size: 9px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent3);
    margin-bottom: 14px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }

  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tech-badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    font-size: 10px;
    padding: 4px 9px;
    border: 1px solid var(--border);
    color: var(--text-dim);
    background: var(--bg);
    transition: border-color 0.15s, color 0.15s;
  }

  .tech-badge:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  .tech-badge .dot-sm {
    width: 5px; height: 5px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
  }

  .tech-badge.c .dot-sm { background: #00599C; }
  .tech-badge.py .dot-sm { background: #3776AB; }
  .tech-badge.docker .dot-sm { background: #0db7ed; }
  .tech-badge.linux .dot-sm { background: #FCC624; }
  .tech-badge.gh .dot-sm { background: #2088FF; }
  .tech-badge.k8s .dot-sm { background: #326ce5; }
  .tech-badge.aws .dot-sm { background: #FF9900; }
  .tech-badge.esp .dot-sm { background: #E7352C; }
  .tech-badge.stm .dot-sm { background: #03234B; }
  .tech-badge.bash .dot-sm { background: #4EAA25; }

  /* ─── SNAKE / CONTRIBUTIONS ─── */
  .snake-section {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 20px;
    margin-bottom: 24px;
    position: relative;
    overflow: hidden;
  }

  .snake-inner {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .snake-inner img {
    max-width: 100%;
    filter: brightness(0.9) saturate(0.8);
  }

  /* ─── FOOTER ─── */
  .footer {
    margin-top: 40px;
    padding-top: 20px;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 10px;
    color: var(--text-dim);
    letter-spacing: 0.05em;
  }

  .footer .signal {
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .signal-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--green);
    animation: pulse 2s ease infinite;
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(61,220,132,0.4); }
    50% { box-shadow: 0 0 0 5px rgba(61,220,132,0); }
  }

  /* ─── ENTRY ANIMATIONS ─── */
  .fade-up {
    opacity: 0;
    transform: translateY(16px);
    animation: fadeUp 0.5s ease forwards;
  }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }
  .delay-5 { animation-delay: 0.5s; }
  .delay-6 { animation-delay: 0.6s; }

  /* ─── HEADER BOTTOM ROW ─── */
  .header-meta {
    display: flex;
    align-items: center;
    gap: 18px;
    flex-wrap: wrap;
    padding: 10px 40px 14px;
    border-top: 1px solid var(--border);
    font-size: 10px;
    color: var(--text-dim);
  }

  .header-meta span { display: flex; align-items: center; gap: 5px; }
  .header-meta span::before { color: var(--accent2); }

  @media (max-width: 640px) {
    .header-body { grid-template-columns: 1fr; }
    .status-block { text-align: left; }
    .header-meta { padding: 10px 20px 14px; }
    .header-body { padding: 24px 20px 20px; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header fade-up">
    <div class="terminal-bar">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <span class="terminal-title">aram@dev ~ profile.md</span>
    </div>
    <div class="header-body">
      <div>
        <div class="prompt-line"><span>~/</span> whoami</div>
        <div class="name-block"><span class="accent-char">A</span>RAM<br><span class="accent-char">K</span>ARIM</div>
        <p class="tagline">
          Building things at the intersection of <strong>low-level hardware</strong> and <strong>high-level automation</strong> —
          from flashing firmware on microcontrollers to deploying containers in the cloud.
        </p>
        <a href="mailto:aramk6827@gmail.com" class="email-badge">aramk6827@gmail.com</a>
      </div>
      <div class="status-block">
        <div class="status-tag open">● available</div>
        <div class="typing-display">
          DevSecOps · Embedded · Automation<span class="cursor"></span>
        </div>
      </div>
    </div>
    <div class="header-meta">
      <span>📍 University of Sulaimani</span>
      <span>⚙ Computer Engineering</span>
      <span>🐳 Docker · K8s · AWS</span>
      <span>🔌 ESP32 · STM32 · Bare-Metal</span>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="fade-up delay-1">
    <div class="section-label"><span class="num">01</span> About</div>
    <div class="card">
      <p class="about-text">
        I'm a Computer Engineering student who gets equally excited about writing a bare-metal interrupt handler
        and wiring up a CI/CD pipeline. I like understanding how things <em>actually</em> work —
        tracing the full stack from electrons to abstractions, from assembly to orchestration layers.
      </p>
      <div class="quote-block">
        <span>"</span>In order to bake a cake you must first create the Universe.<span>"</span>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="fade-up delay-2">
    <div class="section-label"><span class="num">02</span> Projects</div>
    <div class="project-grid">

      <div class="project-card">
        <div class="project-num">project_01</div>
        <div class="project-name">Uni AI Assistant</div>
        <p class="project-desc">
          An AI assistant built for the University of Sulaimani with proper DevOps practices —
          containerized, version-controlled, and CI/CD wired. Built in first year of comp eng.
        </p>
        <div class="tech-pills">
          <span class="pill highlight">Docker</span>
          <span class="pill highlight">GitHub Actions</span>
          <span class="pill highlight">AWS</span>
          <span class="pill">CI/CD</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-num">project_02</div>
        <div class="project-name">
          <a href="https://github.com/AramK0/LC-3_virtual_machine" target="_blank">LC-3 Virtual Machine</a>
        </div>
        <p class="project-desc">
          A working LC-3 computer architecture implementation in C — simulates the instruction set,
          memory model, and I/O. Built to understand what actually happens between code and hardware.
        </p>
        <div class="tech-pills">
          <span class="pill highlight">C</span>
          <span class="pill">Architecture</span>
          <span class="pill">Assembler</span>
          <span class="pill">Systems</span>
        </div>
      </div>

    </div>
  </div>

  <!-- STACK -->
  <div class="fade-up delay-3">
    <div class="section-label"><span class="num">03</span> Stack</div>
    <div class="stack-grid">

      <div class="stack-category">
        <div class="stack-cat-label">Embedded</div>
        <div class="badge-row">
          <span class="tech-badge esp"><span class="dot-sm"></span> ESP32</span>
          <span class="tech-badge stm"><span class="dot-sm"></span> STM32</span>
          <span class="tech-badge c"><span class="dot-sm"></span> C</span>
          <span class="tech-badge c"><span class="dot-sm"></span> C++</span>
        </div>
      </div>

      <div class="stack-category">
        <div class="stack-cat-label">DevOps & Cloud</div>
        <div class="badge-row">
          <span class="tech-badge linux"><span class="dot-sm"></span> Linux</span>
          <span class="tech-badge docker"><span class="dot-sm"></span> Docker</span>
          <span class="tech-badge k8s"><span class="dot-sm"></span> K8s</span>
          <span class="tech-badge aws"><span class="dot-sm"></span> AWS</span>
          <span class="tech-badge gh"><span class="dot-sm"></span> GH Actions</span>
        </div>
      </div>

      <div class="stack-category">
        <div class="stack-cat-label">Languages</div>
        <div class="badge-row">
          <span class="tech-badge py"><span class="dot-sm"></span> Python</span>
          <span class="tech-badge bash"><span class="dot-sm"></span> Bash</span>
          <span class="tech-badge c"><span class="dot-sm"></span> C</span>
        </div>
      </div>

    </div>
  </div>

  <!-- SNAKE / ACTIVITY -->
  <div class="fade-up delay-4">
    <div class="section-label"><span class="num">04</span> Activity</div>
    <div class="snake-section">
      <div class="snake-inner">
        <img
          src="https://raw.githubusercontent.com/AramK0/AramK0/output/github-contribution-grid-snake-dark.svg"
          alt="GitHub contribution snake"
        />
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer fade-up delay-5">
    <div class="signal">
      <div class="signal-dot"></div>
      <span>systems online</span>
    </div>
    <span>Why do it manually if you can script it?</span>
    <span>@AramK0</span>
  </div>

</div>
</body>
</html>
