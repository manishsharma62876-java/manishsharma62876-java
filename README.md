<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Manish Sharma — Java Backend Developer</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0f0d;
    --surface: #111a15;
    --surface2: #172010;
    --border: #1e3020;
    --border2: #2a4030;
    --green: #22c55e;
    --green-dim: #16a34a;
    --green-glow: #22c55e30;
    --teal: #14b8a6;
    --red: #ef4444;
    --amber: #f59e0b;
    --blue: #3b82f6;
    --purple: #a855f7;
    --pink: #ec4899;
    --text: #e2f0e8;
    --text-muted: #6b8f72;
    --text-dim: #3d6647;
    --font-display: 'Syne', sans-serif;
    --font-code: 'JetBrains Mono', monospace;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-code);
    font-size: 14px;
    line-height: 1.7;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(34,197,94,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(34,197,94,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 3rem 2rem 6rem;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    text-align: center;
    margin-bottom: 3rem;
    padding-bottom: 3rem;
    border-bottom: 1px solid var(--border);
    position: relative;
  }

  .header::after {
    content: '';
    position: absolute;
    bottom: -1px;
    left: 50%;
    transform: translateX(-50%);
    width: 120px;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--green), transparent);
  }

  .status-bar {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--green);
    background: var(--green-glow);
    border: 1px solid var(--green-dim);
    border-radius: 2px;
    padding: 4px 14px;
    margin-bottom: 1.5rem;
  }

  .status-dot {
    width: 6px;
    height: 6px;
    background: var(--green);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  h1 {
    font-family: var(--font-display);
    font-size: clamp(2.2rem, 5vw, 3.5rem);
    font-weight: 800;
    line-height: 1.1;
    margin-bottom: 0.5rem;
    background: linear-gradient(135deg, #e2f0e8 0%, #22c55e 50%, #14b8a6 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tagline {
    font-size: 13px;
    color: var(--text-muted);
    letter-spacing: 0.5px;
    margin-bottom: 1.5rem;
  }

  .typing-line {
    font-size: 13px;
    color: var(--green);
    font-family: var(--font-code);
    height: 22px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 4px;
  }

  .typing-line::before { content: '> '; color: var(--text-dim); }

  .cursor {
    display: inline-block;
    width: 8px;
    height: 15px;
    background: var(--green);
    animation: blink 1s step-end infinite;
    vertical-align: middle;
  }

  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

  /* ── SECTION ── */
  .section {
    margin-bottom: 2.5rem;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 1.2rem;
  }

  .section-num {
    font-size: 10px;
    color: var(--green);
    letter-spacing: 1px;
  }

  .section-title {
    font-family: var(--font-display);
    font-size: 17px;
    font-weight: 600;
    color: var(--text);
    letter-spacing: 0.3px;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px;
  }

  .about-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 8px 12px;
    font-size: 12.5px;
    transition: border-color 0.2s;
  }

  .about-item:hover { border-color: var(--border2); }

  .about-item .icon { color: var(--green); font-size: 14px; min-width: 18px; }
  .about-item .label { color: var(--text-muted); min-width: 80px; font-size: 11px; }
  .about-item .val { color: var(--text); }

  /* ── TECH STACK ── */
  .stack-category {
    margin-bottom: 1rem;
  }

  .cat-label {
    font-size: 10px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--text-dim);
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .cat-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    font-size: 11.5px;
    font-weight: 500;
    padding: 4px 10px;
    border-radius: 3px;
    border: 1px solid;
    letter-spacing: 0.3px;
    transition: transform 0.15s, box-shadow 0.15s;
    cursor: default;
  }

  .badge:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
  }

  .badge svg { width: 13px; height: 13px; flex-shrink: 0; }

  .b-java   { background: #1a1000; color: #f59e0b; border-color: #854F0B; }
  .b-spring { background: #0d1a10; color: #22c55e; border-color: #166534; }
  .b-kafka  { background: #1a0d0d; color: #ef4444; border-color: #991b1b; }
  .b-redis  { background: #0d1a13; color: #14b8a6; border-color: #0f766e; }
  .b-db     { background: #0d1220; color: #3b82f6; border-color: #1d4ed8; }
  .b-docker { background: #0d1520; color: #60a5fa; border-color: #1e40af; }
  .b-tools  { background: #160d1a; color: #a855f7; border-color: #7e22ce; }
  .b-fe     { background: #1a0d18; color: #ec4899; border-color: #9d174d; }
  .b-sec    { background: #0d1a10; color: #4ade80; border-color: #15803d; }

  /* ── PROJECTS ── */
  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    overflow: hidden;
    margin-bottom: 1rem;
    transition: border-color 0.2s;
  }

  .project-card:hover { border-color: var(--border2); }

  .project-card:hover .proj-bar { width: 100%; }

  .proj-bar {
    height: 2px;
    background: linear-gradient(90deg, var(--green), var(--teal));
    width: 40px;
    transition: width 0.4s ease;
  }

  .proj-body { padding: 1rem 1.2rem; }

  .proj-title {
    font-family: var(--font-display);
    font-size: 15px;
    font-weight: 600;
    margin-bottom: 4px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .proj-emoji { font-size: 18px; }

  .proj-desc {
    font-size: 12.5px;
    color: var(--text-muted);
    margin-bottom: 12px;
    line-height: 1.6;
  }

  .feat-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 12px;
    margin-bottom: 12px;
  }

  .feat-table tr { border-bottom: 1px solid var(--border); }
  .feat-table tr:last-child { border-bottom: none; }
  .feat-table td { padding: 5px 0; vertical-align: top; }
  .feat-table td:first-child { color: var(--green); width: 36%; padding-right: 12px; font-weight: 500; }
  .feat-table td:last-child { color: var(--text-muted); }

  .tech-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 4px;
    padding-top: 10px;
    border-top: 1px solid var(--border);
  }

  .tech-pill {
    font-size: 10.5px;
    background: rgba(34,197,94,0.07);
    border: 1px solid rgba(34,197,94,0.15);
    color: var(--green);
    border-radius: 2px;
    padding: 2px 8px;
  }

  /* ── LEARNING ── */
  .learn-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px;
  }

  .learn-item {
    display: flex;
    align-items: center;
    gap: 10px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 8px 12px;
    font-size: 12.5px;
    transition: border-color 0.2s;
  }

  .learn-item:hover { border-color: var(--border2); }

  .learn-icon { font-size: 15px; }

  .learn-label { flex: 1; color: var(--text); }

  .status-badge {
    font-size: 9.5px;
    letter-spacing: 0.8px;
    text-transform: uppercase;
    padding: 2px 7px;
    border-radius: 2px;
    font-weight: 500;
    white-space: nowrap;
  }

  .s-prog { background: rgba(34,197,94,0.12); color: var(--green); border: 1px solid rgba(34,197,94,0.25); }
  .s-exp  { background: rgba(168,85,247,0.1);  color: #a855f7; border: 1px solid rgba(168,85,247,0.2); }

  /* ── EXPERTISE ── */
  .expertise-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5px;
  }

  .exp-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 12.5px;
    padding: 5px 0;
    color: var(--text-muted);
  }

  .exp-item::before {
    content: '✓';
    color: var(--green);
    font-weight: 700;
    min-width: 14px;
  }

  /* ── CONNECT ── */
  .connect-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    font-size: 12.5px;
    font-family: var(--font-code);
    padding: 8px 16px;
    border-radius: 4px;
    border: 1px solid var(--border2);
    background: var(--surface);
    color: var(--text);
    text-decoration: none;
    transition: all 0.2s;
  }

  .connect-btn:hover {
    background: var(--surface2);
    border-color: var(--green-dim);
    color: var(--green);
    transform: translateY(-1px);
  }

  .connect-btn svg { width: 15px; height: 15px; }

  /* ── OBJECTIVE ── */
  .objective {
    background: var(--surface);
    border: 1px solid var(--border);
    border-left: 3px solid var(--green);
    border-radius: 0 4px 4px 0;
    padding: 1rem 1.2rem;
    font-size: 13px;
    color: var(--text-muted);
    line-height: 1.8;
  }

  .objective strong { color: var(--text); font-weight: 500; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 2.5rem;
    border-top: 1px solid var(--border);
    margin-top: 3rem;
    color: var(--text-dim);
    font-size: 11.5px;
  }

  .footer-star {
    color: var(--green);
    margin: 4px 0;
    font-size: 12px;
  }

  /* ── STATS PLACEHOLDER ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
    margin-bottom: 1rem;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 12px;
    text-align: center;
  }

  .stat-card .stat-val {
    font-family: var(--font-display);
    font-size: 22px;
    font-weight: 700;
    color: var(--green);
    display: block;
  }

  .stat-card .stat-label {
    font-size: 10.5px;
    color: var(--text-muted);
    letter-spacing: 0.5px;
    text-transform: uppercase;
    margin-top: 2px;
  }

  /* ── DIVIDER ── */
  .divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 2.5rem 0;
    position: relative;
  }

  @media (max-width: 600px) {
    .about-grid, .learn-grid, .expertise-list, .stats-grid { grid-template-columns: 1fr; }
    h1 { font-size: 2rem; }
  }

  /* fade-in animation */
  .section {
    opacity: 0;
    transform: translateY(12px);
    animation: fadeUp 0.5s forwards;
  }
  .section:nth-child(1) { animation-delay: 0.05s; }
  .section:nth-child(2) { animation-delay: 0.12s; }
  .section:nth-child(3) { animation-delay: 0.18s; }
  .section:nth-child(4) { animation-delay: 0.24s; }
  .section:nth-child(5) { animation-delay: 0.30s; }
  .section:nth-child(6) { animation-delay: 0.36s; }
  .section:nth-child(7) { animation-delay: 0.42s; }
  .section:nth-child(8) { animation-delay: 0.48s; }
  .section:nth-child(9) { animation-delay: 0.54s; }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HEADER -->
  <header class="header">
    <div class="status-bar">
      <span class="status-dot"></span>
      Open to Java Backend Opportunities
    </div>
    <h1>Manish Sharma</h1>
    <p class="tagline">Java Backend Developer &nbsp;·&nbsp; Spring Boot &nbsp;·&nbsp; Kafka &nbsp;·&nbsp; Redis &nbsp;·&nbsp; Microservices &nbsp;·&nbsp; Hyderabad, India</p>
    <div class="typing-line">
      <span id="typed"></span><span class="cursor"></span>
    </div>
  </header>

  <!-- ABOUT -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">01</span>
      <h2 class="section-title">👨‍💻 About Me</h2>
      <div class="section-line"></div>
    </div>
    <div class="about-grid">
      <div class="about-item"><span class="icon">🌱</span><span class="val">Currently learning Spring Security, JWT, Kafka & Microservices</span></div>
      <div class="about-item"><span class="icon">💻</span><span class="val">Focused on backend development & event-driven systems</span></div>
      <div class="about-item"><span class="icon">📚</span><span class="val">1 year intensive training — Naresh i Technologies, Hyderabad</span></div>
      <div class="about-item"><span class="icon">🚀</span><span class="val">Passionate about scalable REST APIs & distributed architecture</span></div>
      <div class="about-item"><span class="icon">🔭</span><span class="val">Exploring React.js to complement backend skills with UI</span></div>
      <div class="about-item"><span class="icon">🎯</span><span class="val">Open to Java Backend Developer roles</span></div>
      <div class="about-item"><span class="icon">📍</span><span class="val">Based in Hyderabad, India</span></div>
      <div class="about-item"><span class="icon">📫</span><span class="val">manish62876@gmail.com</span></div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">02</span>
      <h2 class="section-title">🛠️ Tech Stack</h2>
      <div class="section-line"></div>
    </div>

    <div class="stack-category">
      <div class="cat-label">Languages</div>
      <div class="badge-row">
        <span class="badge b-java">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M8.851 18.56s-.917.534.653.714c1.902.218 2.874.187 4.969-.211 0 0 .552.346 1.321.646-4.699 2.013-10.633-.118-6.943-1.149M8.276 15.933s-1.028.761.542.924c2.032.209 3.636.227 6.413-.308 0 0 .384.389.987.602-5.679 1.661-12.007.13-7.942-1.218M13.116 11.475c1.158 1.333-.304 2.533-.304 2.533s2.939-1.518 1.589-3.418c-1.261-1.772-2.228-2.652 3.007-5.688 0 0-8.216 2.051-4.292 6.573M19.33 20.504s.679.559-.747.991c-2.712.822-11.288 1.069-13.669.033-.856-.373.75-.89 1.254-.998.527-.114.828-.093.828-.093-.953-.671-6.156 1.317-2.643 1.887 9.58 1.553 17.462-.7 14.977-1.82M9.292 13.21s-4.362 1.036-1.544 1.412c1.189.159 3.561.123 5.772-.062 1.806-.152 3.618-.477 3.618-.477s-.637.272-1.098.587c-4.429 1.165-12.986.623-10.522-.568 2.082-1.006 3.774-.892 3.774-.892M17.116 17.584c4.503-2.34 2.421-4.589.968-4.285-.355.074-.515.138-.515.138s.132-.207.385-.297c2.875-1.011 5.086 2.981-.928 4.562 0 0 .07-.063.09-.118M14.401 0s2.494 2.494-2.365 6.33c-3.896 3.077-.888 4.832-.001 6.836-2.274-2.053-3.943-3.858-2.824-5.539 1.644-2.469 6.197-3.665 5.19-7.627M9.734 23.924c4.322.277 10.959-.153 11.116-2.198 0 0-.302.775-3.572 1.391-3.688.694-8.239.613-10.937.168 0 0 .553.457 3.393.639"/></svg>
          Java
        </span>
        <span class="badge b-db">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 4.24 2 7v10c0 2.76 4.48 5 10 5s10-2.24 10-5V7c0-2.76-4.48-5-10-5zm0 2c4.42 0 8 1.79 8 4s-3.58 4-8 4-8-1.79-8-4 3.58-4 8-4zM4 9.86C5.72 11.15 8.65 12 12 12s6.28-.85 8-2.14V12c0 2.21-3.58 4-8 4s-8-1.79-8-4V9.86zm0 5C5.72 16.15 8.65 17 12 17s6.28-.85 8-2.14V17c0 2.21-3.58 4-8 4s-8-1.79-8-4v-2.14z"/></svg>
          SQL
        </span>
        <span class="badge b-fe">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M3 3h18v18H3V3zm16.525 13.707c-.131-.821-.666-1.511-2.252-2.155-.552-.259-1.165-.438-1.349-.854-.068-.248-.078-.382-.034-.529.113-.484.687-.629 1.137-.495.293.09.563.315.732.676.775-.507.775-.507 1.316-.844-.203-.314-.304-.451-.439-.586-.473-.528-1.103-.798-2.126-.775l-.528.067c-.507.124-.991.395-1.283.754-.855.968-.608 2.655.427 3.354 1.023.765 2.521.933 2.712 1.653.18.878-.652 1.159-1.475 1.058-.607-.136-.945-.439-1.316-1.002l-1.372.788c.157.359.337.517.607.832 1.305 1.316 4.567 1.249 5.153-.754.021-.067.18-.528.056-1.237l.034.049zm-6.737-5.434h-1.686c0 1.453-.007 2.898-.007 4.354 0 .924.047 1.772-.104 2.033-.247.517-.886.451-1.175.359-.297-.146-.448-.349-.623-.641-.047-.078-.082-.146-.095-.146l-1.368.844c.229.473.563.879.994 1.137.641.383 1.502.507 2.404.305.588-.17 1.095-.519 1.358-1.059.384-.697.302-1.553.299-2.509.008-1.541 0-3.083 0-4.627v.03z"/></svg>
          JavaScript
        </span>
        <span class="badge b-fe">HTML / CSS</span>
      </div>
    </div>

    <div class="stack-category">
      <div class="cat-label">Backend Frameworks</div>
      <div class="badge-row">
        <span class="badge b-spring">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.59 4.76a9.91 9.91 0 01-1.86 2.74A9.16 9.16 0 0020.85 12a9.17 9.17 0 01-9.17 9.17A9.17 9.17 0 012.5 12a9.17 9.17 0 019.18-9.17 9 9 0 014 .93 12.37 12.37 0 002.88-2.19zM9.97 15.41a1.29 1.29 0 01-1-.41 2 2 0 01-.38-1.3 3.76 3.76 0 01.28-1.56 2.07 2.07 0 011.74-1.25 1.35 1.35 0 011.09.5 2.24 2.24 0 01.39 1.41 3.47 3.47 0 01-.41 1.66 2 2 0 01-1.71.95zm4.94-4.57h-1.46l-.7 3.52a1.33 1.33 0 00-.05.31c0 .26.12.4.35.4a1.09 1.09 0 00.55-.22l.12.89a2.56 2.56 0 01-1.49.46 1 1 0 01-.79-.31 1.25 1.25 0 01-.27-.87 5.47 5.47 0 01.07-.71l.74-3.47h-.84l.16-.85h.84l.29-1.39 1.48-.45-.39 1.84h1.47z"/></svg>
          Spring Boot
        </span>
        <span class="badge b-sec">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4zm0 2.18l7 3.12V11c0 4.52-3.02 8.79-7 10.93C8.02 19.79 5 15.52 5 11V6.3l7-3.12zM12 7a2 2 0 100 4 2 2 0 000-4zm0 6c-2 0-4 1-4 2v1h8v-1c0-1-2-2-4-2z"/></svg>
          Spring Security
        </span>
        <span class="badge b-spring">Spring Data JPA</span>
        <span class="badge b-spring">Hibernate</span>
        <span class="badge b-spring">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 14H9V8h2v8zm4 0h-2V8h2v8z"/></svg>
          JWT Auth
        </span>
      </div>
    </div>

    <div class="stack-category">
      <div class="cat-label">Messaging & Caching</div>
      <div class="badge-row">
        <span class="badge b-kafka">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
          Apache Kafka
        </span>
        <span class="badge b-redis">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M10.5 1.5l1.5 5h5l-4 3 1.5 5-4-3-4 3 1.5-5-4-3h5z"/></svg>
          Redis
        </span>
      </div>
    </div>

    <div class="stack-category">
      <div class="cat-label">Frontend (Learning)</div>
      <div class="badge-row">
        <span class="badge b-fe">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M14.23 12.004a2.236 2.236 0 01-2.235 2.236 2.236 2.236 0 01-2.236-2.236 2.236 2.236 0 012.235-2.236 2.236 2.236 0 012.236 2.236zm2.648-10.69c-1.346 0-3.107.96-4.888 2.622-1.78-1.653-3.542-2.602-4.887-2.602-.41 0-.783.093-1.106.278-1.375.793-1.683 3.264-.973 6.365C1.98 8.917 0 10.42 0 12.004c0 1.59 1.99 3.097 5.043 4.03-.704 3.113-.39 5.588.988 6.38.32.187.69.275 1.102.275 1.345 0 3.107-.96 4.888-2.624 1.78 1.654 3.542 2.603 4.887 2.603.41 0 .783-.09 1.106-.275 1.374-.792 1.683-3.263.973-6.365C22.02 15.096 24 13.59 24 12.004c0-1.59-1.99-3.097-5.043-4.032.704-3.11.39-5.587-.988-6.38-.318-.184-.688-.277-1.092-.278zm-.005 1.09c.278 0 .513.06.739.187.746.43 1.027 1.913.7 3.907-.03.18-.066.368-.104.556-.73-.168-1.522-.3-2.35-.393-.476-.648-.97-1.262-1.473-1.833 1.155-1.045 2.244-1.424 2.488-1.424zm-9.888 0c.242 0 1.33.375 2.487 1.42-.496.57-.99 1.184-1.467 1.831-.83.094-1.622.225-2.35.393-.038-.187-.073-.374-.104-.55-.33-1.994-.048-3.48.7-3.91.224-.127.46-.184.734-.184zm4.944 3.073a18.3 18.3 0 012.252.271c-.325.67-.673 1.356-1.044 2.038-.37.682-.77 1.348-1.188 1.994-.44-.007-.883-.01-1.337-.01-.453 0-.896.003-1.336.01-.418-.646-.82-1.31-1.19-1.992-.373-.68-.72-1.367-1.045-2.038.72-.122 1.473-.215 2.252-.27.43-.025.866-.04 1.319-.04.454 0 .89.015 1.317.037zm-5.32 3.143c.26.58.541 1.165.846 1.748.304.578.625 1.148.963 1.702-.457-.112-.896-.244-1.313-.393-.42-1.046-.625-2.178-.496-3.057zm10.64 0c.13.879-.076 2.011-.496 3.057-.417.149-.856.28-1.313.393.338-.554.659-1.124.963-1.702.305-.583.587-1.168.846-1.748zm-1.29 4.053c-.325.67-.673 1.356-1.044 2.038-.37.682-.77 1.348-1.188 1.994-.44-.007-.883-.01-1.337-.01-.453 0-.896.003-1.336.01-.418-.646-.82-1.31-1.19-1.992-.373-.68-.72-1.367-1.045-2.038.72-.122 1.473-.215 2.252-.27.43-.025.866-.04 1.319-.04.454 0 .89.015 1.317.037zm-4.68 2.9c-.496.57-.99 1.184-1.467 1.831-.83.094-1.622.225-2.35.393-.038-.187-.073-.374-.104-.55-.33-1.994-.048-3.48.7-3.91.224-.127.46-.184.734-.184.242 0 1.33.375 2.487 1.42zm5.31 0c1.155 1.045 2.244 1.424 2.488 1.424.278 0 .513.06.739.187.746.43 1.027 1.913.7 3.907-.03.18-.066.368-.104.556-.73-.168-1.522-.3-2.35-.393-.476-.648-.97-1.262-1.473-1.833z"/></svg>
          React.js
        </span>
        <span class="badge b-fe">HTML5 / CSS3</span>
        <span class="badge b-fe">Responsive Design</span>
      </div>
    </div>

    <div class="stack-category">
      <div class="cat-label">Database</div>
      <div class="badge-row">
        <span class="badge b-db">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 4.24 2 7v10c0 2.76 4.48 5 10 5s10-2.24 10-5V7c0-2.76-4.48-5-10-5zm0 2c4.42 0 8 1.79 8 4s-3.58 4-8 4-8-1.79-8-4 3.58-4 8-4zm0 14c-4.42 0-8-1.79-8-4v-2.14C5.72 13.15 8.65 14 12 14s6.28-.85 8-2.14V16c0 2.21-3.58 4-8 4z"/></svg>
          MySQL
        </span>
        <span class="badge b-redis">Redis (Cache Layer)</span>
      </div>
    </div>

    <div class="stack-category">
      <div class="cat-label">Tools & Platforms</div>
      <div class="badge-row">
        <span class="badge b-tools">Maven</span>
        <span class="badge b-tools">Git / GitHub</span>
        <span class="badge b-tools">Postman</span>
        <span class="badge b-tools">Swagger / OpenAPI</span>
        <span class="badge b-tools">IntelliJ IDEA</span>
        <span class="badge b-docker">Docker (learning)</span>
        <span class="badge b-tools">SonarQube</span>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">03</span>
      <h2 class="section-title">🚀 Projects</h2>
      <div class="section-line"></div>
    </div>

    <div class="project-card">
      <div class="proj-bar"></div>
      <div class="proj-body">
        <div class="proj-title"><span class="proj-emoji">🍔</span> Food Delivery Management System</div>
        <p class="proj-desc">Event-driven backend built with Spring Boot. Uses Apache Kafka for async order status events, Redis for caching frequently accessed menu data, and JWT-secured endpoints.</p>
        <table class="feat-table">
          <tr><td>User Management</td><td>Registration, login, JWT-secured sessions with RBAC</td></tr>
          <tr><td>Restaurant & Menu</td><td>Full CRUD with Redis caching layer for performance</td></tr>
          <tr><td>Order Processing</td><td>End-to-end lifecycle; Kafka topics for async status events</td></tr>
          <tr><td>Notifications</td><td>Kafka consumer for real-time order confirmation events</td></tr>
          <tr><td>Validation & Docs</td><td>Bean validation + global exception handler + Swagger UI</td></tr>
        </table>
        <div class="tech-pills">
          <span class="tech-pill">Java</span>
          <span class="tech-pill">Spring Boot</span>
          <span class="tech-pill">Spring Security</span>
          <span class="tech-pill">Apache Kafka</span>
          <span class="tech-pill">Redis</span>
          <span class="tech-pill">JWT</span>
          <span class="tech-pill">MySQL</span>
          <span class="tech-pill">Maven</span>
          <span class="tech-pill">Swagger</span>
        </div>
      </div>
    </div>

    <div class="project-card">
      <div class="proj-bar"></div>
      <div class="proj-body">
        <div class="proj-title"><span class="proj-emoji">🏥</span> Hospital Management System</div>
        <p class="proj-desc">Backend for managing patients, doctors, and appointments with role-based access control, Kafka-driven appointment notifications, and clean DTO-based API contracts.</p>
        <table class="feat-table">
          <tr><td>Patient & Doctor CRUD</td><td>Full lifecycle management with pagination support</td></tr>
          <tr><td>Appointment Scheduling</td><td>Book, update, cancel with conflict detection logic</td></tr>
          <tr><td>RBAC</td><td>Admin, Doctor, Patient role authorization via Spring Security</td></tr>
          <tr><td>Kafka Notifications</td><td>Async appointment confirmation & reminder events</td></tr>
          <tr><td>API Docs</td><td>Full Swagger / OpenAPI documentation</td></tr>
        </table>
        <div class="tech-pills">
          <span class="tech-pill">Java</span>
          <span class="tech-pill">Spring Boot</span>
          <span class="tech-pill">Spring Security</span>
          <span class="tech-pill">Apache Kafka</span>
          <span class="tech-pill">Redis</span>
          <span class="tech-pill">MySQL</span>
          <span class="tech-pill">Maven</span>
          <span class="tech-pill">Swagger</span>
        </div>
      </div>
    </div>
  </section>

  <!-- LEARNING -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">04</span>
      <h2 class="section-title">📚 Currently Learning</h2>
      <div class="section-line"></div>
    </div>
    <div class="learn-grid">
      <div class="learn-item"><span class="learn-icon">🔐</span><span class="learn-label">Spring Security & JWT</span><span class="status-badge s-prog">In Progress</span></div>
      <div class="learn-item"><span class="learn-icon">🔑</span><span class="learn-label">Role-Based Auth (RBAC)</span><span class="status-badge s-prog">In Progress</span></div>
      <div class="learn-item"><span class="learn-icon">📨</span><span class="learn-label">Apache Kafka</span><span class="status-badge s-prog">In Progress</span></div>
      <div class="learn-item"><span class="learn-icon">⚡</span><span class="learn-label">Redis Caching</span><span class="status-badge s-prog">In Progress</span></div>
      <div class="learn-item"><span class="learn-icon">🧩</span><span class="learn-label">Microservices Architecture</span><span class="status-badge s-exp">Exploring</span></div>
      <div class="learn-item"><span class="learn-icon">🐳</span><span class="learn-label">Docker Fundamentals</span><span class="status-badge s-exp">Exploring</span></div>
      <div class="learn-item"><span class="learn-icon">⚛️</span><span class="learn-label">React.js Basics</span><span class="status-badge s-exp">Exploring</span></div>
      <div class="learn-item"><span class="learn-icon">📐</span><span class="learn-label">System Design</span><span class="status-badge s-exp">Exploring</span></div>
    </div>
  </section>

  <!-- EXPERTISE -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">05</span>
      <h2 class="section-title">💡 Core Java Expertise</h2>
      <div class="section-line"></div>
    </div>
    <div class="expertise-list">
      <div class="exp-item">OOP Concepts & Design Principles</div>
      <div class="exp-item">Collections Framework</div>
      <div class="exp-item">Exception Handling</div>
      <div class="exp-item">Multithreading & Concurrency</div>
      <div class="exp-item">Java 8 — Lambda, Stream API</div>
      <div class="exp-item">Functional Interfaces & Optional</div>
      <div class="exp-item">JDBC, Servlets, JSP (Basics)</div>
      <div class="exp-item">REST API Design & Best Practices</div>
      <div class="exp-item">Event-Driven Architecture (Kafka)</div>
      <div class="exp-item">Caching Strategies (Redis)</div>
    </div>
  </section>

  <!-- GITHUB STATS -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">06</span>
      <h2 class="section-title">📊 GitHub Stats</h2>
      <div class="section-line"></div>
    </div>
    <div style="display:flex; flex-direction:column; gap:8px;">
      <img src="https://github-readme-stats.vercel.app/api?username=manishsharma62876-java&show_icons=true&theme=dark&bg_color=111a15&title_color=22c55e&icon_color=14b8a6&text_color=e2f0e8&border_color=1e3020&hide_border=false" alt="GitHub Stats" style="border-radius:6px; max-width:100%; display:block;" />
      <img src="https://github-readme-streak-stats.herokuapp.com?user=manishsharma62876-java&theme=dark&background=111a15&ring=22c55e&fire=14b8a6&currStreakLabel=22c55e&border=1e3020&stroke=1e3020&dates=6b8f72&sideLabels=22c55e&sideNums=e2f0e8&currStreakNum=e2f0e8" alt="Streak Stats" style="border-radius:6px; max-width:100%; display:block;" />
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=manishsharma62876-java&layout=compact&theme=dark&bg_color=111a15&title_color=22c55e&text_color=e2f0e8&border_color=1e3020" alt="Top Languages" style="border-radius:6px; max-width:100%; display:block;" />
    </div>
  </section>

  <!-- CONNECT -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">07</span>
      <h2 class="section-title">🤝 Connect With Me</h2>
      <div class="section-line"></div>
    </div>
    <div class="connect-row">
      <a class="connect-btn" href="mailto:manish62876@gmail.com">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
        manish62876@gmail.com
      </a>
      <a class="connect-btn" href="https://github.com/manishsharma62876-java" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2A10 10 0 002 12c0 4.42 2.87 8.17 6.84 9.5.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34-.46-1.16-1.11-1.47-1.11-1.47-.91-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.87 1.52 2.34 1.07 2.91.83.09-.65.35-1.09.63-1.34-2.22-.25-4.55-1.11-4.55-4.92 0-1.11.38-2 1.03-2.71-.1-.25-.45-1.29.1-2.64 0 0 .84-.27 2.75 1.02.79-.22 1.65-.33 2.5-.33.85 0 1.71.11 2.5.33 1.91-1.29 2.75-1.02 2.75-1.02.55 1.35.2 2.39.1 2.64.65.71 1.03 1.6 1.03 2.71 0 3.82-2.34 4.66-4.57 4.91.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0012 2z"/></svg>
        GitHub
      </a>
      <a class="connect-btn" href="https://linkedin.com" target="_blank">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
    </div>
  </section>

  <!-- OBJECTIVE -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">08</span>
      <h2 class="section-title">🎯 Career Objective</h2>
      <div class="section-line"></div>
    </div>
    <div class="objective">
      Seeking a <strong>Java Backend Developer</strong> role where I can apply my knowledge of <strong>Java, Spring Boot, Apache Kafka, Redis, and REST APIs</strong> — while growing into <strong>Microservices architecture</strong> and contributing to impactful, scalable software solutions that solve real-world problems.
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <div style="margin-bottom: 8px;">
      <img src="https://komarev.com/ghpvc/?username=manishsharma62876-java&label=Profile+Views&color=22c55e&style=flat" alt="Profile Views" style="border-radius:3px;" />
    </div>
    <div class="footer-star">⭐ If you find my work interesting, feel free to star my repositories! ⭐</div>
    <div style="margin-top: 10px; color: var(--text-dim); font-size: 11px;">
      Built with Java &nbsp;·&nbsp; Powered by Spring Boot &nbsp;·&nbsp; Fuelled by Kafka & Redis
    </div>
  </footer>

</div>

<script>
  const phrases = [
    'Java Backend Developer',
    'Spring Boot Enthusiast',
    'Kafka & Redis Practitioner',
    'REST API Craftsman',
    'Open to New Opportunities'
  ];
  let pi = 0, ci = 0, del = false;
  const el = document.getElementById('typed');

  function type() {
    const cur = phrases[pi];
    if (!del) {
      el.textContent = cur.slice(0, ++ci);
      if (ci === cur.length) { del = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = cur.slice(0, --ci);
      if (ci === 0) { del = false; pi = (pi + 1) % phrases.length; }
    }
    setTimeout(type, del ? 40 : 75);
  }
  type();
</script>
</body>
</html>
