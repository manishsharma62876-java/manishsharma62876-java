<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Manish Sharma | Java Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --navy: #0A0F1E;
    --navy2: #0F1629;
    --navy3: #141B35;
    --violet: #7C3AED;
    --violet-light: #A78BFA;
    --cyan: #06B6D4;
    --cyan-light: #67E8F9;
    --pink: #EC4899;
    --pink-light: #F9A8D4;
    --gold: #F59E0B;
    --gold-light: #FCD34D;
    --green: #10B981;
    --white: #F8FAFC;
    --muted: #94A3B8;
    --card: rgba(255,255,255,0.04);
    --border: rgba(255,255,255,0.08);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--navy);
    color: var(--white);
    font-family: 'Inter', sans-serif;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ── SCROLLBAR ── */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--navy); }
  ::-webkit-scrollbar-thumb { background: var(--violet); border-radius: 3px; }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 2rem;
    background: rgba(10,15,30,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 700; font-size: 1.2rem;
    background: linear-gradient(135deg, var(--violet-light), var(--cyan));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .nav-links { display: flex; gap: 1.5rem; list-style: none; }
  .nav-links a {
    color: var(--muted); text-decoration: none; font-size: 0.875rem; font-weight: 500;
    transition: color .2s;
  }
  .nav-links a:hover { color: var(--cyan); }
  .nav-cta {
    background: linear-gradient(135deg, var(--violet), var(--pink));
    color: white; border: none; padding: .5rem 1.25rem; border-radius: 8px;
    font-size: .875rem; font-weight: 600; cursor: pointer; text-decoration: none;
    transition: opacity .2s, transform .2s;
  }
  .nav-cta:hover { opacity: .85; transform: translateY(-1px); }
  .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; }
  .hamburger span { width: 22px; height: 2px; background: var(--white); border-radius: 2px; transition: all .3s; }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: flex; align-items: center; justify-content: center;
    padding: 6rem 2rem 4rem;
    position: relative; overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0; z-index: 0;
    background:
      radial-gradient(ellipse 80% 60% at 20% 30%, rgba(124,58,237,0.18) 0%, transparent 60%),
      radial-gradient(ellipse 60% 50% at 80% 70%, rgba(6,182,212,0.15) 0%, transparent 55%),
      radial-gradient(ellipse 40% 40% at 50% 90%, rgba(236,72,153,0.1) 0%, transparent 50%);
  }
  .grid-lines {
    position: absolute; inset: 0; z-index: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
  }
  .hero-content { position: relative; z-index: 1; text-align: center; max-width: 800px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: .5rem;
    background: rgba(124,58,237,0.15); border: 1px solid rgba(124,58,237,0.4);
    padding: .4rem 1rem; border-radius: 50px; font-size: .8rem; font-weight: 500;
    color: var(--violet-light); margin-bottom: 1.5rem;
    animation: fadeDown .6s ease both;
  }
  .hero-badge::before { content: ''; width: 7px; height: 7px; background: var(--green); border-radius: 50%; animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:.5;transform:scale(1.3)} }
  .hero-name {
    font-family: 'Space Grotesk', sans-serif;
    font-size: clamp(2.8rem, 7vw, 5.5rem);
    font-weight: 700; line-height: 1.05; letter-spacing: -2px;
    animation: fadeDown .7s .1s ease both;
  }
  .hero-name .gradient-text {
    background: linear-gradient(135deg, var(--cyan) 0%, var(--violet-light) 40%, var(--pink) 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    background-size: 200% 200%; animation: gradShift 4s ease infinite;
  }
  @keyframes gradShift { 0%,100%{background-position:0% 50%} 50%{background-position:100% 50%} }
  .hero-title {
    font-size: clamp(1rem, 2.5vw, 1.3rem); color: var(--muted); margin: 1rem 0 1.5rem;
    font-weight: 400; animation: fadeDown .7s .2s ease both;
  }
  .hero-title span { color: var(--cyan-light); font-weight: 600; }
  .hero-desc {
    font-size: 1rem; color: rgba(148,163,184,0.9); max-width: 580px; margin: 0 auto 2.5rem;
    line-height: 1.75; animation: fadeDown .7s .3s ease both;
  }
  .hero-tags {
    display: flex; flex-wrap: wrap; gap: .6rem; justify-content: center;
    margin-bottom: 2.5rem; animation: fadeDown .7s .4s ease both;
  }
  .hero-tag {
    padding: .3rem .9rem; border-radius: 50px; font-size: .78rem; font-weight: 600;
    font-family: 'JetBrains Mono', monospace; letter-spacing: .03em;
  }
  .tag-violet { background: rgba(124,58,237,.2); border: 1px solid rgba(124,58,237,.5); color: var(--violet-light); }
  .tag-cyan   { background: rgba(6,182,212,.15); border: 1px solid rgba(6,182,212,.45); color: var(--cyan-light); }
  .tag-pink   { background: rgba(236,72,153,.15); border: 1px solid rgba(236,72,153,.45); color: var(--pink-light); }
  .tag-gold   { background: rgba(245,158,11,.15); border: 1px solid rgba(245,158,11,.45); color: var(--gold-light); }
  .tag-green  { background: rgba(16,185,129,.15); border: 1px solid rgba(16,185,129,.45); color: #6EE7B7; }
  .hero-buttons { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; animation: fadeDown .7s .5s ease both; }
  .btn-primary {
    display: inline-flex; align-items: center; gap: .5rem;
    background: linear-gradient(135deg, var(--violet), var(--pink));
    color: white; padding: .75rem 2rem; border-radius: 10px;
    font-weight: 600; font-size: .95rem; text-decoration: none;
    transition: transform .2s, box-shadow .2s;
    box-shadow: 0 0 20px rgba(124,58,237,.4);
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 0 35px rgba(124,58,237,.6); }
  .btn-secondary {
    display: inline-flex; align-items: center; gap: .5rem;
    border: 1px solid var(--border); color: var(--white); padding: .75rem 2rem; border-radius: 10px;
    font-weight: 600; font-size: .95rem; text-decoration: none; background: var(--card);
    transition: border-color .2s, transform .2s;
  }
  .btn-secondary:hover { border-color: var(--cyan); transform: translateY(-2px); }

  @keyframes fadeDown { from{opacity:0;transform:translateY(-20px)} to{opacity:1;transform:translateY(0)} }

  /* ── STATS BAR ── */
  .stats-bar {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 1px; background: var(--border);
    border-top: 1px solid var(--border); border-bottom: 1px solid var(--border);
  }
  .stat-item {
    background: var(--navy2); padding: 1.5rem 1rem; text-align: center;
    transition: background .2s;
  }
  .stat-item:hover { background: rgba(124,58,237,.08); }
  .stat-number {
    font-family: 'Space Grotesk', sans-serif; font-size: 1.8rem; font-weight: 700;
    background: linear-gradient(135deg, var(--cyan), var(--violet-light));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }
  .stat-label { font-size: .8rem; color: var(--muted); margin-top: .2rem; }

  /* ── SECTIONS ── */
  section { padding: 5rem 2rem; }
  .container { max-width: 1100px; margin: 0 auto; }
  .section-header { text-align: center; margin-bottom: 3.5rem; }
  .section-eye {
    display: inline-block; font-family: 'JetBrains Mono', monospace;
    font-size: .75rem; font-weight: 500; letter-spacing: .1em; text-transform: uppercase;
    margin-bottom: .75rem; padding: .25rem .75rem; border-radius: 4px;
  }
  .eye-violet { color: var(--violet-light); background: rgba(124,58,237,.15); }
  .eye-cyan   { color: var(--cyan-light);   background: rgba(6,182,212,.12); }
  .eye-pink   { color: var(--pink-light);   background: rgba(236,72,153,.12); }
  .eye-gold   { color: var(--gold-light);   background: rgba(245,158,11,.12); }
  .section-title {
    font-family: 'Space Grotesk', sans-serif;
    font-size: clamp(1.8rem, 4vw, 2.8rem); font-weight: 700; letter-spacing: -1px;
  }
  .section-sub { color: var(--muted); margin-top: .6rem; font-size: 1rem; }

  /* ── ABOUT ── */
  #about { background: var(--navy2); }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: center; }
  .about-avatar {
    aspect-ratio: 1; border-radius: 20px; background: linear-gradient(135deg, var(--violet), var(--pink), var(--cyan));
    padding: 3px; max-width: 320px; margin: 0 auto; width: 100%;
  }
  .avatar-inner {
    background: var(--navy2); border-radius: 18px; height: 100%;
    display: flex; align-items: center; justify-content: center;
    font-size: 6rem;
  }
  .about-text h3 { font-family: 'Space Grotesk', sans-serif; font-size: 1.4rem; font-weight: 600; margin-bottom: 1rem; }
  .about-text p { color: var(--muted); line-height: 1.8; margin-bottom: 1rem; }
  .about-list { list-style: none; }
  .about-list li {
    display: flex; align-items: flex-start; gap: .75rem;
    padding: .6rem 0; color: var(--muted); font-size: .95rem;
    border-bottom: 1px solid var(--border);
  }
  .about-list li:last-child { border-bottom: none; }
  .about-list li .icon { font-size: 1rem; flex-shrink: 0; margin-top: .1rem; }
  .about-list li strong { color: var(--white); }
  .contact-links { display: flex; flex-wrap: wrap; gap: .75rem; margin-top: 1.5rem; }
  .contact-link {
    display: inline-flex; align-items: center; gap: .5rem;
    padding: .5rem 1rem; border-radius: 8px; font-size: .85rem; font-weight: 500;
    text-decoration: none; transition: transform .2s, box-shadow .2s;
    border: 1px solid var(--border); background: var(--card); color: var(--white);
  }
  .contact-link:hover { transform: translateY(-2px); }
  .contact-link.linkedin { border-color: rgba(10,102,194,.5); }
  .contact-link.linkedin:hover { box-shadow: 0 0 16px rgba(10,102,194,.35); }
  .contact-link.github { border-color: rgba(255,255,255,.2); }
  .contact-link.github:hover { box-shadow: 0 0 16px rgba(255,255,255,.1); }
  .contact-link.email { border-color: rgba(236,72,153,.4); }
  .contact-link.email:hover { box-shadow: 0 0 16px rgba(236,72,153,.3); }

  /* ── SKILLS ── */
  #skills { background: var(--navy); }
  .skills-tabs { display: flex; flex-wrap: wrap; gap: .5rem; justify-content: center; margin-bottom: 2.5rem; }
  .tab-btn {
    padding: .45rem 1.1rem; border-radius: 8px; font-size: .85rem; font-weight: 600;
    cursor: pointer; transition: all .2s; border: 1px solid var(--border);
    background: var(--card); color: var(--muted); font-family: 'Inter', sans-serif;
  }
  .tab-btn.active, .tab-btn:hover { background: var(--violet); border-color: var(--violet); color: white; }
  .skills-panel { display: none; }
  .skills-panel.active { display: block; }
  .skills-grid { display: flex; flex-wrap: wrap; gap: .75rem; }
  .skill-chip {
    display: inline-flex; align-items: center; gap: .5rem;
    padding: .55rem 1rem; border-radius: 8px; font-size: .85rem; font-weight: 500;
    transition: transform .2s, box-shadow .2s; cursor: default;
    font-family: 'JetBrains Mono', monospace;
  }
  .skill-chip:hover { transform: translateY(-2px); }
  .skill-chip.c-violet { background: rgba(124,58,237,.15); border: 1px solid rgba(124,58,237,.4); color: var(--violet-light); }
  .skill-chip.c-violet:hover { box-shadow: 0 0 14px rgba(124,58,237,.3); }
  .skill-chip.c-cyan { background: rgba(6,182,212,.1); border: 1px solid rgba(6,182,212,.35); color: var(--cyan-light); }
  .skill-chip.c-cyan:hover { box-shadow: 0 0 14px rgba(6,182,212,.25); }
  .skill-chip.c-pink { background: rgba(236,72,153,.1); border: 1px solid rgba(236,72,153,.35); color: var(--pink-light); }
  .skill-chip.c-pink:hover { box-shadow: 0 0 14px rgba(236,72,153,.25); }
  .skill-chip.c-gold { background: rgba(245,158,11,.1); border: 1px solid rgba(245,158,11,.35); color: var(--gold-light); }
  .skill-chip.c-gold:hover { box-shadow: 0 0 14px rgba(245,158,11,.25); }
  .skill-chip.c-green { background: rgba(16,185,129,.1); border: 1px solid rgba(16,185,129,.35); color: #6EE7B7; }
  .skill-chip.c-green:hover { box-shadow: 0 0 14px rgba(16,185,129,.25); }

  /* ── PROJECTS ── */
  #projects { background: var(--navy2); }
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.5rem; }
  .project-card {
    background: var(--navy3); border: 1px solid var(--border); border-radius: 16px;
    padding: 1.75rem; transition: transform .25s, box-shadow .25s, border-color .25s;
    position: relative; overflow: hidden;
  }
  .project-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: var(--gradient); border-radius: 16px 16px 0 0;
  }
  .project-card.p-violet::before { background: linear-gradient(90deg, var(--violet), var(--cyan)); }
  .project-card.p-pink::before   { background: linear-gradient(90deg, var(--pink), var(--gold)); }
  .project-card.p-cyan::before   { background: linear-gradient(90deg, var(--cyan), var(--green)); }
  .project-card.p-gold::before   { background: linear-gradient(90deg, var(--gold), var(--pink)); }
  .project-card:hover { transform: translateY(-5px); }
  .project-card.p-violet:hover { box-shadow: 0 20px 40px rgba(124,58,237,.2); border-color: rgba(124,58,237,.3); }
  .project-card.p-pink:hover   { box-shadow: 0 20px 40px rgba(236,72,153,.2); border-color: rgba(236,72,153,.3); }
  .project-card.p-cyan:hover   { box-shadow: 0 20px 40px rgba(6,182,212,.2); border-color: rgba(6,182,212,.3); }
  .project-card.p-gold:hover   { box-shadow: 0 20px 40px rgba(245,158,11,.2); border-color: rgba(245,158,11,.3); }
  .project-icon { font-size: 2rem; margin-bottom: 1rem; }
  .project-title {
    font-family: 'Space Grotesk', sans-serif; font-size: 1.15rem; font-weight: 700;
    margin-bottom: .5rem;
  }
  .project-desc { color: var(--muted); font-size: .88rem; line-height: 1.65; margin-bottom: 1.25rem; }
  .project-stack { display: flex; flex-wrap: wrap; gap: .4rem; margin-bottom: 1.25rem; }
  .stack-tag {
    padding: .2rem .6rem; border-radius: 5px; font-size: .75rem; font-weight: 600;
    font-family: 'JetBrains Mono', monospace; background: rgba(255,255,255,.06); color: var(--muted);
  }
  .project-features { list-style: none; }
  .project-features li {
    color: var(--muted); font-size: .85rem; padding: .3rem 0;
    display: flex; align-items: center; gap: .5rem;
  }
  .project-features li::before { content: '✓'; color: var(--green); font-weight: 700; }

  /* ── LEARNING ── */
  #learning { background: var(--navy); }
  .learning-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1rem; }
  .learning-card {
    background: var(--card); border: 1px solid var(--border); border-radius: 12px;
    padding: 1.5rem 1.25rem; text-align: center;
    transition: transform .2s, box-shadow .2s; cursor: default;
  }
  .learning-card:hover { transform: translateY(-4px); }
  .learning-icon { font-size: 2.2rem; margin-bottom: .75rem; }
  .learning-name { font-weight: 600; font-size: .95rem; margin-bottom: .4rem; }
  .learning-tag {
    display: inline-block; font-size: .7rem; padding: .15rem .6rem; border-radius: 50px;
    font-weight: 600; font-family: 'JetBrains Mono', monospace;
  }
  .tag-in-progress { background: rgba(245,158,11,.15); color: var(--gold-light); border: 1px solid rgba(245,158,11,.3); }
  .lc-violet:hover { box-shadow: 0 12px 30px rgba(124,58,237,.25); border-color: rgba(124,58,237,.3); }
  .lc-cyan:hover   { box-shadow: 0 12px 30px rgba(6,182,212,.2); border-color: rgba(6,182,212,.3); }
  .lc-pink:hover   { box-shadow: 0 12px 30px rgba(236,72,153,.2); border-color: rgba(236,72,153,.3); }
  .lc-gold:hover   { box-shadow: 0 12px 30px rgba(245,158,11,.2); border-color: rgba(245,158,11,.3); }
  .lc-green:hover  { box-shadow: 0 12px 30px rgba(16,185,129,.2); border-color: rgba(16,185,129,.3); }

  /* ── CTA ── */
  #cta {
    background: var(--navy2);
    text-align: center; padding: 6rem 2rem;
    position: relative; overflow: hidden;
  }
  #cta::before {
    content: ''; position: absolute; inset: 0; z-index: 0;
    background:
      radial-gradient(ellipse 60% 80% at 50% 50%, rgba(124,58,237,.12) 0%, transparent 65%);
  }
  .cta-content { position: relative; z-index: 1; max-width: 600px; margin: 0 auto; }
  .cta-title {
    font-family: 'Space Grotesk', sans-serif;
    font-size: clamp(2rem, 5vw, 3.5rem); font-weight: 700; letter-spacing: -1px;
    margin-bottom: 1rem;
  }
  .cta-sub { color: var(--muted); font-size: 1.05rem; margin-bottom: 2.5rem; }
  .cta-buttons { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }

  /* ── FOOTER ── */
  footer {
    background: var(--navy); border-top: 1px solid var(--border);
    text-align: center; padding: 2rem;
    color: var(--muted); font-size: .85rem;
  }
  footer span { color: var(--pink); }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    .nav-links, .nav-cta { display: none; }
    .hamburger { display: flex; }
    .about-grid { grid-template-columns: 1fr; }
    .about-avatar { max-width: 200px; }
    .projects-grid { grid-template-columns: 1fr; }
    nav { padding: 1rem 1.25rem; }
    section { padding: 4rem 1.25rem; }
  }
  @media (max-width: 480px) {
    .hero-buttons { flex-direction: column; align-items: center; }
    .hero-buttons a { width: 100%; text-align: center; justify-content: center; }
    .stats-bar { grid-template-columns: 1fr 1fr; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">&lt;Manish /&gt;</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#learning">Learning</a></li>
  </ul>
  <a href="mailto:manishsharma62876@gmail.com" class="nav-cta">Hire Me</a>
  <button class="hamburger" onclick="toggleMenu()" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="grid-lines"></div>
  <div class="hero-content">
    <div class="hero-badge">Available for Opportunities</div>
    <h1 class="hero-name">
      <span class="gradient-text">Manish Sharma</span>
    </h1>
    <p class="hero-title">
      <span>Java Full Stack Developer</span> · Spring Boot · Microservices · React.js
    </p>
    <p class="hero-desc">
      Passionate about building scalable, secure, production-ready web applications
      with clean and efficient code. Based in Hyderabad, India 🇮🇳
    </p>
    <div class="hero-tags">
      <span class="hero-tag tag-violet">Spring Boot</span>
      <span class="hero-tag tag-cyan">Microservices</span>
      <span class="hero-tag tag-pink">React.js</span>
      <span class="hero-tag tag-gold">JWT Auth</span>
      <span class="hero-tag tag-green">Docker</span>
      <span class="hero-tag tag-violet">Spring Security</span>
      <span class="hero-tag tag-cyan">MySQL</span>
      <span class="hero-tag tag-pink">Kubernetes</span>
    </div>
    <div class="hero-buttons">
      <a href="#projects" class="btn-primary">🚀 View Projects</a>
      <a href="mailto:manishsharma62876@gmail.com" class="btn-secondary">📧 Get In Touch</a>
    </div>
  </div>
</section>

<!-- STATS -->
<div class="stats-bar">
  <div class="stat-item">
    <div class="stat-number">4+</div>
    <div class="stat-label">Projects Built</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">20+</div>
    <div class="stat-label">Technologies</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">30+</div>
    <div class="stat-label">Skills & Concepts</div>
  </div>
  <div class="stat-item">
    <div class="stat-number">∞</div>
    <div class="stat-label">Eager to Learn</div>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="about-grid">
      <div>
        <div class="about-avatar">
          <div class="avatar-inner">👨‍💻</div>
        </div>
      </div>
      <div class="about-text">
        <div class="section-eye eye-violet">About Me</div>
        <h2 class="section-title" style="text-align:left;margin-bottom:1rem;">Hello, I'm Manish 👋</h2>
        <p>Full Stack Developer specialising in Java, Spring Boot, and Microservices — building applications that are secure, scalable, and production-ready.</p>
        <p>Currently deepening my expertise in Docker, Kubernetes, Kafka, and System Design while actively seeking opportunities to create real-world impact.</p>
        <ul class="about-list">
          <li><span class="icon">📧</span><div><strong>Email:</strong> manishsharma62876@gmail.com</div></li>
          <li><span class="icon">📱</span><div><strong>Phone:</strong> +91 9572114007</div></li>
          <li><span class="icon">📍</span><div><strong>Location:</strong> Hyderabad, India</div></li>
          <li><span class="icon">🌱</span><div><strong>Learning:</strong> Microservices · Docker · Kubernetes · Kafka</div></li>
        </ul>
        <div class="contact-links">
          <a href="https://www.linkedin.com/in/manish-sharma-6964a0383/" class="contact-link linkedin" target="_blank">💼 LinkedIn</a>
          <a href="https://github.com/manishsharma62876-java" class="contact-link github" target="_blank">🐱 GitHub</a>
          <a href="mailto:manishsharma62876@gmail.com" class="contact-link email">✉️ Email</a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="section-header">
      <div class="section-eye eye-cyan">Tech Stack</div>
      <h2 class="section-title">Skills & Technologies</h2>
      <p class="section-sub">Click a category to explore</p>
    </div>
    <div class="skills-tabs">
      <button class="tab-btn active" onclick="showTab('backend')">Backend</button>
      <button class="tab-btn" onclick="showTab('frontend')">Frontend</button>
      <button class="tab-btn" onclick="showTab('microservices')">Microservices</button>
      <button class="tab-btn" onclick="showTab('devops')">DevOps & Tools</button>
      <button class="tab-btn" onclick="showTab('concepts')">Concepts</button>
    </div>

    <div id="tab-backend" class="skills-panel active">
      <div class="skills-grid">
        <span class="skill-chip c-violet">☕ Java</span>
        <span class="skill-chip c-violet">🌱 Spring Boot</span>
        <span class="skill-chip c-violet">🔒 Spring Security</span>
        <span class="skill-chip c-violet">📦 Spring Data JPA</span>
        <span class="skill-chip c-violet">🌐 Spring MVC</span>
        <span class="skill-chip c-cyan">🗄️ Hibernate</span>
        <span class="skill-chip c-cyan">🔌 JDBC</span>
        <span class="skill-chip c-cyan">📡 REST APIs</span>
        <span class="skill-chip c-cyan">🛡️ JWT Auth</span>
        <span class="skill-chip c-pink">🗃️ MySQL</span>
        <span class="skill-chip c-pink">📐 DTO Pattern</span>
        <span class="skill-chip c-pink">⚠️ Exception Handling</span>
        <span class="skill-chip c-gold">🏗️ Servlets</span>
        <span class="skill-chip c-gold">📋 Validation</span>
        <span class="skill-chip c-green">🔨 Maven</span>
        <span class="skill-chip c-green">🧵 Multithreading</span>
      </div>
    </div>

    <div id="tab-frontend" class="skills-panel">
      <div class="skills-grid">
        <span class="skill-chip c-cyan">⚛️ React.js</span>
        <span class="skill-chip c-cyan">🌐 HTML5</span>
        <span class="skill-chip c-cyan">🎨 CSS3</span>
        <span class="skill-chip c-violet">📜 JavaScript</span>
        <span class="skill-chip c-violet">🅱️ Bootstrap</span>
        <span class="skill-chip c-pink">💨 Tailwind CSS</span>
        <span class="skill-chip c-gold">🔣 SQL</span>
      </div>
    </div>

    <div id="tab-microservices" class="skills-panel">
      <div class="skills-grid">
        <span class="skill-chip c-violet">☁️ Spring Cloud</span>
        <span class="skill-chip c-violet">🔍 Eureka Server</span>
        <span class="skill-chip c-violet">🔗 Eureka Client</span>
        <span class="skill-chip c-cyan">🚪 API Gateway</span>
        <span class="skill-chip c-cyan">🤝 OpenFeign</span>
        <span class="skill-chip c-cyan">⚙️ Config Server</span>
        <span class="skill-chip c-pink">🛡️ Resilience4j</span>
        <span class="skill-chip c-pink">📡 Service Discovery</span>
        <span class="skill-chip c-gold">🔄 Inter-Service Comm.</span>
        <span class="skill-chip c-green">🚀 Independent Deploy</span>
      </div>
    </div>

    <div id="tab-devops" class="skills-panel">
      <div class="skills-grid">
        <span class="skill-chip c-cyan">🐳 Docker</span>
        <span class="skill-chip c-violet">☸️ Kubernetes</span>
        <span class="skill-chip c-pink">🐧 Linux</span>
        <span class="skill-chip c-gold">📦 Git</span>
        <span class="skill-chip c-gold">🐱 GitHub</span>
        <span class="skill-chip c-green">💡 IntelliJ IDEA</span>
        <span class="skill-chip c-green">🌙 VS Code</span>
        <span class="skill-chip c-violet">🧪 Postman</span>
        <span class="skill-chip c-cyan">🌑 Eclipse</span>
      </div>
    </div>

    <div id="tab-concepts" class="skills-panel">
      <div class="skills-grid">
        <span class="skill-chip c-violet">🧩 OOPs</span>
        <span class="skill-chip c-violet">📚 Collections Framework</span>
        <span class="skill-chip c-violet">🔄 Java 8 Features</span>
        <span class="skill-chip c-cyan">🌊 Streams API</span>
        <span class="skill-chip c-cyan">λ Lambda Expressions</span>
        <span class="skill-chip c-cyan">❓ Optional Class</span>
        <span class="skill-chip c-pink">📊 Comparable & Comparator</span>
        <span class="skill-chip c-pink">🏛️ Microservices Architecture</span>
        <span class="skill-chip c-gold">🔐 Role-Based Auth</span>
        <span class="skill-chip c-gold">🌐 RESTful Services</span>
        <span class="skill-chip c-green">🌍 Global Exception Handling</span>
        <span class="skill-chip c-green">⚡ Multithreading</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="section-header">
      <div class="section-eye eye-pink">Work</div>
      <h2 class="section-title">Featured Projects</h2>
      <p class="section-sub">Applications built with real-world requirements in mind</p>
    </div>
    <div class="projects-grid">

      <div class="project-card p-violet">
        <div class="project-icon">👥</div>
        <h3 class="project-title">Employee Management System</h3>
        <p class="project-desc">A comprehensive REST API system for managing employee data with full CRUD capabilities, data validation, and clean DTO-based architecture.</p>
        <div class="project-stack">
          <span class="stack-tag">Java</span>
          <span class="stack-tag">Spring Boot</span>
          <span class="stack-tag">Spring Data JPA</span>
          <span class="stack-tag">MySQL</span>
        </div>
        <ul class="project-features">
          <li>CRUD Operations</li>
          <li>Input Validation</li>
          <li>Global Exception Handling</li>
          <li>DTO Pattern</li>
          <li>REST APIs</li>
        </ul>
      </div>

      <div class="project-card p-pink">
        <div class="project-icon">🔐</div>
        <h3 class="project-title">JWT Authentication System</h3>
        <p class="project-desc">Secure authentication system with JWT token-based auth, role-based access control, and full user registration and login workflow.</p>
        <div class="project-stack">
          <span class="stack-tag">Spring Security</span>
          <span class="stack-tag">JWT</span>
          <span class="stack-tag">Spring Boot</span>
          <span class="stack-tag">MySQL</span>
        </div>
        <ul class="project-features">
          <li>User Registration</li>
          <li>Login Authentication</li>
          <li>JWT Token Generation</li>
          <li>Role-Based Authorization</li>
          <li>Secure REST APIs</li>
        </ul>
      </div>

      <div class="project-card p-cyan">
        <div class="project-icon">📋</div>
        <h3 class="project-title">Employee CRUD Application</h3>
        <p class="project-desc">Clean and efficient employee data management application using Hibernate ORM for seamless database operations.</p>
        <div class="project-stack">
          <span class="stack-tag">Spring Boot</span>
          <span class="stack-tag">Hibernate</span>
          <span class="stack-tag">MySQL</span>
        </div>
        <ul class="project-features">
          <li>Add Employee</li>
          <li>Update Employee</li>
          <li>Delete Employee</li>
          <li>Get by ID / Get All</li>
        </ul>
      </div>

      <div class="project-card p-gold">
        <div class="project-icon">🌐</div>
        <h3 class="project-title">Microservices Project</h3>
        <p class="project-desc">A distributed microservices architecture with service discovery, centralized routing, and resilient inter-service communication patterns.</p>
        <div class="project-stack">
          <span class="stack-tag">Spring Cloud</span>
          <span class="stack-tag">Eureka</span>
          <span class="stack-tag">API Gateway</span>
          <span class="stack-tag">OpenFeign</span>
        </div>
        <ul class="project-features">
          <li>Service Discovery</li>
          <li>Centralized Routing</li>
          <li>Inter-Service Communication</li>
          <li>Independent Deployment</li>
        </ul>
      </div>

    </div>
  </div>
</section>

<!-- LEARNING -->
<section id="learning">
  <div class="container">
    <div class="section-header">
      <div class="section-eye eye-gold">Growth</div>
      <h2 class="section-title">Currently Learning 🔥</h2>
      <p class="section-sub">Constantly levelling up the stack</p>
    </div>
    <div class="learning-grid">
      <div class="learning-card lc-violet">
        <div class="learning-icon">☸️</div>
        <div class="learning-name">Kubernetes</div>
        <span class="learning-tag tag-in-progress">In Progress</span>
      </div>
      <div class="learning-card lc-cyan">
        <div class="learning-icon">🐳</div>
        <div class="learning-name">Docker</div>
        <span class="learning-tag tag-in-progress">In Progress</span>
      </div>
      <div class="learning-card lc-pink">
        <div class="learning-icon">📨</div>
        <div class="learning-name">Apache Kafka</div>
        <span class="learning-tag tag-in-progress">In Progress</span>
      </div>
      <div class="learning-card lc-gold">
        <div class="learning-icon">🏗️</div>
        <div class="learning-name">System Design</div>
        <span class="learning-tag tag-in-progress">In Progress</span>
      </div>
      <div class="learning-card lc-green">
        <div class="learning-icon">🧩</div>
        <div class="learning-name">Design Patterns</div>
        <span class="learning-tag tag-in-progress">In Progress</span>
      </div>
      <div class="learning-card lc-violet">
        <div class="learning-icon">🌩️</div>
        <div class="learning-name">Microservices</div>
        <span class="learning-tag tag-in-progress">Deepening</span>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section id="cta">
  <div class="cta-content">
    <div class="section-eye eye-violet" style="display:inline-block;margin-bottom:.75rem;">Open to Work</div>
    <h2 class="cta-title">Let's Build Something<br><span style="background:linear-gradient(135deg,var(--cyan),var(--violet-light),var(--pink));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">Amazing Together</span></h2>
    <p class="cta-sub">Looking for a Java Full Stack Developer role where I can build scalable, production-grade applications while continuously growing as an engineer.</p>
    <div class="cta-buttons">
      <a href="mailto:manishsharma62876@gmail.com" class="btn-primary">✉️ Email Me</a>
      <a href="https://www.linkedin.com/in/manish-sharma-6964a0383/" class="btn-secondary" target="_blank">💼 LinkedIn</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>Built with <span>♥</span> by Manish Sharma · Hyderabad, India · 2025</p>
  <p style="margin-top:.4rem;opacity:.6;">Code · Learn · Build · Grow ⭐</p>
</footer>

<script>
  function showTab(name) {
    document.querySelectorAll('.skills-panel').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('tab-' + name).classList.add('active');
    event.target.classList.add('active');
  }

  function toggleMenu() {
    const links = document.querySelector('.nav-links');
    const cta = document.querySelector('.nav-cta');
    if (links) {
      const open = links.style.display === 'flex';
      links.style.cssText = open ? '' : 'display:flex;flex-direction:column;position:fixed;top:60px;left:0;right:0;background:rgba(10,15,30,0.97);padding:1.5rem 2rem;gap:1rem;border-bottom:1px solid rgba(255,255,255,0.08);z-index:99;backdrop-filter:blur(20px)';
      if(cta) cta.style.display = open ? 'none' : 'block';
    }
  }

  // Scroll-reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.08 });

  document.querySelectorAll('.project-card, .learning-card, .stat-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(24px)';
    el.style.transition = 'opacity .5s ease, transform .5s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
