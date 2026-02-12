<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aram Karim</title>
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
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: 'JetBrains Mono', monospace;
  min-height: 100vh;
  overflow-x: hidden;
}
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
body::after {
  content: '';
  position: fixed;
  inset: 0;
  background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.04) 2px, rgba(0,0,0,0.04) 4px);
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
.header {
  border: 1px solid var(--border);
  background: var(--surface);
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
.dot { width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0; }
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
.prompt-line { font-size: 11px; color: var(--text-dim); margin-bottom: 6px; letter-spacing: 0.05em; }
.prompt-line span { color: var(--accent); }
.name-block {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(52px, 8vw, 88px);
  letter-spacing: 0.04em;
  color: var(--text-bright);
  line-height: 0.9;
  margin-bottom: 16px;
}
.name-block .ac { color: var(--accent); }
.tagline {
  font-size: 12.5px;
  color: var(--text-dim);
  line-height: 1.7;
  max-width: 480px;
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 300;
  margin-bottom: 20px;
}
.tagline strong { color: var(--text); font-weight: 600; }
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
  text-decoration: none;
}
.status-block { text-align: right; }
.status-tag {
  display: inline-block;
  font-size: 9.5px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  padding: 4px 10px;
  border: 1px solid rgba(61,220,132,0.3);
  color: var(--green);
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
.cursor {
  display: inline-block;
  width: 7px;
  height: 12px;
  background: var(--accent);
  vertical-align: middle;
  animation: blink 1s step-end infinite;
  margin-left: 2px;
}
@keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }
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
.section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }
.section-label .num { color: var(--text-dim); font-size: 9px; }
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
.project-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 14px;
  margin-bottom: 24px;
}
.project-card {
  border: 1px solid var(--border);
  background: var(--surface);
  padding: 20px 22px;
  position: relative;
  overflow: hidden;
  transition: border-color 0.2s, background 0.2s;
}
.project-card:hover { border-color: rgba(106,159,181,0.4); background: var(--surface2); }
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
.project-num { font-size: 9px; color: var(--text-dim); letter-spacing: 0.1em; margin-bottom: 8px; }
.project-name { font-size: 13px; font-weight: 500; color: var(--text-bright); margin-bottom: 8px; letter-spacing: 0.02em; }
.project-name a { color: inherit; text-decoration: none; }
.project-name a:hover { color: var(--accent2); }
.project-name a::after { content: ' \2197'; font-size: 10px; opacity: 0.6; }
.project-desc {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 11.5px;
  font-weight: 300;
  color: var(--text-dim);
  line-height: 1.65;
  margin-bottom: 14px;
}
.tech-pills { display: flex; flex-wrap: wrap; gap: 5px; }
.pill {
  font-size: 9px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 3px 8px;
  border: 1px solid var(--border);
  color: var(--text-dim);
  background: var(--bg);
}
.pill.hl { border-color: rgba(106,159,181,0.3); color: var(--accent); background: rgba(106,159,181,0.06); }
.stack-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 14px;
  margin-bottom: 24px;
}
.stack-cat { border: 1px solid var(--border); background: var(--surface); padding: 18px 18px 16px; }
.stack-cat-label {
  font-size: 9px;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--accent3);
  margin-bottom: 14px;
  padding-bottom: 8px;
  border-bottom: 1px solid var(--border);
}
.badge-row { display: flex; flex-wrap: wrap; gap: 6px; }
.tb {
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
.tb:hover { border-color: var(--accent); color: var(--accent); }
.ds { width: 5px; height: 5px; border-radius: 50%; flex-shrink: 0; }
.snake-section {
  border: 1px solid var(--border);
  background: var(--surface);
  padding: 20px;
  margin-bottom: 24px;
  overflow: hidden;
}
.snake-inner { display: flex; align-items: center; justify-content: center; }
.snake-inner img { max-width: 100%; filter: brightness(0.9) saturate(0.8); }
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
.signal { display: flex; align-items: center; gap: 6px; }
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
.fu { opacity: 0; transform: translateY(16px); animation: fadeUp 0.5s ease forwards; }
@keyframes fadeUp { to { opacity: 1; transform: translateY(0); } }
.d1 { animation-delay: 0.05s; }
.d2 { animation-delay: 0.15s; }
.d3 { animation-delay: 0.25s; }
.d4 { animation-delay: 0.35s; }
.d5 { animation-delay: 0.45s; }
.d6 { animation-delay: 0.55s; }
@media (max-width: 640px) {
  .header-body { grid-template-columns: 1fr; padding: 24px 20px 20px; }
  .status-block { text-align: left; }
  .header-meta { padding: 10px 20px 14px; }
  .project-grid { grid-template-columns: 1fr; }
  .stack-grid { grid-template-columns: 1fr; }
  .footer { flex-direction: column; gap: 8px; text-align: center; }
}
</style>
</head>
<body>
<div class="container">

  <div class="header fu d1">
    <div class="terminal-bar">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <span class="terminal-title">aram@dev &nbsp;&#126;&nbsp; profile.md</span>
    </div>
    <div class="header-body">
      <div>
        <div class="prompt-line"><span>&#126;/</span> whoami</div>
        <div class="name-block"><span class="ac">A</span>RAM<br><span class="ac">K</span>ARIM</div>
        <p class="tagline">
          Building things at the intersection of <strong>low-level hardware</strong> and <strong>high-level automation</strong> &#8212;
          from flashing firmware on microcontrollers to deploying containers in the cloud.
        </p>
        <a href="mailto:aramk6827@gmail.com" class="email-badge">&#9993; &nbsp;aramk6827@gmail.com</a>
      </div>
      <div class="status-block">
        <div class="status-tag">&#9679; available</div>
        <div class="typing-display">DevSecOps &middot; Embedded &middot; Automation<span class="cursor"></span></div>
      </div>
    </div>
    <div class="header-meta">
      <span>&#128205; University of Sulaimani</span>
      <span>&nbsp;&nbsp;&#9881; Computer Engineering</span>
      <span>&nbsp;&nbsp;&#128051; Docker &middot; K8s &middot; AWS</span>
      <span>&nbsp;&nbsp;&#128268; ESP32 &middot; STM32 &middot; Bare-Metal</span>
    </div>
  </div>

  <div class="fu d2">
    <div class="section-label"><span class="num">01</span> About</div>
    <div class="card">
      <p class="about-text">
        I'm a Computer Engineering student who gets equally excited about writing a bare-metal interrupt handler
        and wiring up a CI/CD pipeline. I like understanding how things <em>actually</em> work &#8212;
        tracing the full stack from electrons to abstractions, from assembly to orchestration layers.
      </p>
      <div class="quote-block">
        &#8220;In order to bake a cake you must first create the Universe.&#8221;
      </div>
    </div>
  </div>

  <div class="fu d3">
    <div class="section-label"><span class="num">02</span> Projects</div>
    <div class="project-grid">
      <div class="project-card">
        <div class="project-num">project_01</div>
        <div class="project-name">Uni AI Assistant</div>
        <p class="project-desc">
          An AI assistant built for the University of Sulaimani with proper DevOps practices &#8212;
          containerized, version-controlled, and CI/CD wired. Built in first year of comp eng.
        </p>
        <div class="tech-pills">
          <span class="pill hl">Docker</span>
          <span class="pill hl">GitHub Actions</span>
          <span class="pill hl">AWS</span>
          <span class="pill">CI/CD</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-num">project_02</div>
        <div class="project-name">
          <a href="https://github.com/AramK0/LC-3_virtual_machine" target="_blank">LC-3 Virtual Machine</a>
        </div>
        <p class="project-desc">
          A working LC-3 computer architecture implementation in C &#8212; simulates the instruction set,
          memory model, and I/O. Built to understand what actually happens between code and hardware.
        </p>
        <div class="tech-pills">
          <span class="pill hl">C</span>
          <span class="pill">Architecture</span>
          <span class="pill">Assembler</span>
          <span class="pill">Systems</span>
        </div>
      </div>
    </div>
  </div>

  <div class="fu d4">
    <div class="section-label"><span class="num">03</span> Stack</div>
    <div class="stack-grid">
      <div class="stack-cat">
        <div class="stack-cat-label">Embedded</div>
        <div class="badge-row">
          <span class="tb"><span class="ds" style="background:#E7352C"></span>ESP32</span>
          <span class="tb"><span class="ds" style="background:#03234B"></span>STM32</span>
          <span class="tb"><span class="ds" style="background:#00599C"></span>C</span>
          <span class="tb"><span class="ds" style="background:#00599C"></span>C++</span>
        </div>
      </div>
      <div class="stack-cat">
        <div class="stack-cat-label">DevOps &amp; Cloud</div>
        <div class="badge-row">
          <span class="tb"><span class="ds" style="background:#FCC624"></span>Linux</span>
          <span class="tb"><span class="ds" style="background:#0db7ed"></span>Docker</span>
          <span class="tb"><span class="ds" style="background:#326ce5"></span>K8s</span>
          <span class="tb"><span class="ds" style="background:#FF9900"></span>AWS</span>
          <span class="tb"><span class="ds" style="background:#2088FF"></span>GH Actions</span>
        </div>
      </div>
      <div class="stack-cat">
        <div class="stack-cat-label">Languages</div>
        <div class="badge-row">
          <span class="tb"><span class="ds" style="background:#3776AB"></span>Python</span>
          <span class="tb"><span class="ds" style="background:#4EAA25"></span>Bash</span>
          <span class="tb"><span class="ds" style="background:#00599C"></span>C</span>
        </div>
      </div>
    </div>
  </div>

  <div class="fu d5">
    <div class="section-label"><span class="num">04</span> Activity</div>
    <div class="snake-section">
      <div class="snake-inner">
        <img
          src="https://raw.githubusercontent.com/AramK0/AramK0/output/github-contribution-grid-snake-dark.svg"
          alt="GitHub contribution snake"
          onerror="this.style.display='none';this.parentElement.innerHTML='<span style=&quot;font-size:11px;color:#5a7385&quot;>&#128013; Snake animation renders on GitHub</span>'"
        />
      </div>
    </div>
  </div>

  <div class="footer fu d6">
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
