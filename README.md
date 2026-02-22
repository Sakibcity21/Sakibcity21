<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sakib Sayyad — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Funnel+Sans:ital,wght@0,300..800;1,300..800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #03060f;
    --surface: #060c1a;
    --card: #091223;
    --border: #112240;
    --accent: #60a5fa;
    --accent-bright: #93c5fd;
    --accent-deep: #1d4ed8;
    --accent-vivid: #3b82f6;
    --text: #e2eaf8;
    --muted: #4d6a9a;
    --font-sans: 'Funnel Sans', sans-serif;
    --font-mono: 'DM Mono', monospace;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-sans);
    min-height: 100vh;
    padding: 48px 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 50% at 50% -10%, rgba(29,78,216,0.18) 0%, transparent 60%),
      radial-gradient(ellipse 60% 40% at 80% 100%, rgba(37,99,235,0.1) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
  }

  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image: radial-gradient(rgba(96,165,250,0.07) 1px, transparent 1px);
    background-size: 28px 28px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    width: 100%;
    max-width: 760px;
    display: flex;
    flex-direction: column;
    gap: 16px;
    position: relative;
    z-index: 1;
  }

  /* HEADER */
  .header {
    display: flex;
    align-items: center;
    gap: 28px;
    padding: 36px 40px;
    background: linear-gradient(135deg, #091223 0%, #0a1830 100%);
    border: 1px solid var(--border);
    border-radius: 22px;
    position: relative;
    overflow: hidden;
  }

  .header::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(29,78,216,0.07) 0%, transparent 60%);
    pointer-events: none;
  }

  .header::after {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 260px; height: 260px;
    background: radial-gradient(circle, rgba(59,130,246,0.14) 0%, transparent 65%);
    pointer-events: none;
  }

  .header-glow {
    position: absolute;
    top: 0; left: 40px; right: 40px;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(96,165,250,0.6), transparent);
  }

  .avatar {
    width: 72px; height: 72px;
    border-radius: 50%;
    background: linear-gradient(135deg, #1d4ed8, #60a5fa);
    display: flex; align-items: center; justify-content: center;
    font-size: 24px; font-weight: 800; color: #fff;
    flex-shrink: 0;
    letter-spacing: -1px;
    box-shadow: 0 0 0 4px rgba(96,165,250,0.12), 0 0 24px rgba(59,130,246,0.3);
  }

  .header-info { flex: 1; }

  .name {
    font-size: 28px;
    font-weight: 800;
    letter-spacing: -0.5px;
    line-height: 1.1;
    margin-bottom: 8px;
  }

  .name span {
    background: linear-gradient(90deg, #93c5fd, #60a5fa);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tagline {
    font-family: var(--font-mono);
    font-size: 11.5px;
    color: var(--muted);
    letter-spacing: 0.4px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .status-dot {
    display: inline-block;
    width: 7px; height: 7px;
    background: var(--accent);
    border-radius: 50%;
    box-shadow: 0 0 6px rgba(96,165,250,0.8);
    animation: pulse 2.2s ease-in-out infinite;
    flex-shrink: 0;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; box-shadow: 0 0 6px rgba(96,165,250,0.8); }
    50% { opacity: 0.5; box-shadow: 0 0 2px rgba(96,165,250,0.3); }
  }

  /* ABOUT GRID */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  .about-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 18px 20px;
    display: flex;
    align-items: flex-start;
    gap: 14px;
    transition: border-color 0.25s, background 0.25s;
    cursor: default;
  }

  .about-item:hover {
    border-color: rgba(96,165,250,0.45);
    background: rgba(9,18,35,0.9);
  }

  .about-icon { font-size: 18px; flex-shrink: 0; margin-top: 2px; }

  .about-label {
    font-family: var(--font-mono);
    font-size: 9px;
    color: var(--accent);
    letter-spacing: 1.5px;
    text-transform: uppercase;
    margin-bottom: 5px;
    opacity: 0.8;
  }

  .about-text { font-size: 13px; color: var(--text); line-height: 1.4; font-weight: 600; }

  /* SECTION LABEL */
  .section-label {
    font-family: var(--font-mono);
    font-size: 9.5px;
    color: var(--muted);
    letter-spacing: 2.5px;
    text-transform: uppercase;
    padding: 0 4px;
    margin-top: 4px;
  }

  /* TECH CARD */
  .tech-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 22px;
    padding: 28px 32px;
  }

  .tech-card-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 24px;
  }

  .tech-card-title { font-size: 16px; font-weight: 700; letter-spacing: -0.3px; }

  .tech-badge {
    font-family: var(--font-mono);
    font-size: 10px;
    color: var(--accent);
    background: rgba(96,165,250,0.08);
    border: 1px solid rgba(96,165,250,0.22);
    padding: 4px 12px;
    border-radius: 99px;
  }

  .tech-group { margin-bottom: 22px; }
  .tech-group:last-child { margin-bottom: 0; }

  .tech-group-label {
    font-family: var(--font-mono);
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 1.8px;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .tech-icons { display: flex; flex-wrap: wrap; gap: 8px; }

  .tech-icon {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 7px 14px;
    background: rgba(6,12,26,0.8);
    border: 1px solid var(--border);
    border-radius: 10px;
    font-size: 12.5px;
    font-weight: 600;
    color: var(--text);
    cursor: default;
    transition: all 0.22s;
    white-space: nowrap;
  }

  .tech-icon:hover {
    border-color: rgba(96,165,250,0.5);
    background: rgba(29,78,216,0.08);
    transform: translateY(-2px);
    box-shadow: 0 4px 16px rgba(59,130,246,0.12);
  }

  .tech-icon svg { width: 16px; height: 16px; flex-shrink: 0; }

  /* SOCIALS */
  .socials-row { display: flex; gap: 10px; flex-wrap: wrap; }

  .social-link {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 13px 20px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    text-decoration: none;
    color: var(--text);
    font-size: 13px;
    font-weight: 600;
    transition: all 0.22s;
    flex: 1;
    min-width: 120px;
    justify-content: center;
  }

  .social-link:hover {
    border-color: rgba(96,165,250,0.45);
    background: rgba(29,78,216,0.08);
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(59,130,246,0.1);
  }

  .social-link svg { width: 18px; height: 18px; }

  /* STATS */
  .stats-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 22px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 50%; transform: translateX(-50%);
    width: 60%; height: 1px;
    background: linear-gradient(90deg, transparent, rgba(96,165,250,0.4), transparent);
  }

  .stat-num {
    font-size: 30px;
    font-weight: 800;
    letter-spacing: -1.5px;
    background: linear-gradient(135deg, #93c5fd, #3b82f6);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
    margin-bottom: 7px;
  }

  .stat-desc { font-family: var(--font-mono); font-size: 10px; color: var(--muted); }

  /* FUN FACT */
  .fun-fact {
    background: linear-gradient(135deg, rgba(9,18,35,0.9), rgba(17,34,64,0.7));
    border: 1px solid rgba(29,78,216,0.35);
    border-radius: 16px;
    padding: 20px 26px;
    display: flex;
    align-items: center;
    gap: 18px;
    position: relative;
    overflow: hidden;
  }

  .fun-fact::after {
    content: '';
    position: absolute;
    bottom: -30px; right: -30px;
    width: 120px; height: 120px;
    background: radial-gradient(circle, rgba(59,130,246,0.1), transparent 70%);
  }

  .fun-fact-icon { font-size: 22px; }

  .fun-fact-text {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
    line-height: 1.6;
  }

  .fun-fact-text strong { color: var(--accent-bright); font-weight: 500; }

  @media (max-width: 520px) {
    .about-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr 1fr; }
    .header { flex-direction: column; text-align: center; padding: 28px 24px; }
    .tagline { justify-content: center; }
    .tech-card { padding: 22px 20px; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HEADER -->
  <div class="header">
    <div class="header-glow"></div>
    <div class="avatar">SS</div>
    <div class="header-info">
      <div class="name">Sakib <span>Sayyad</span></div>
      <div class="tagline">
        <span class="status-dot"></span>Full Stack Dev · Learning · Building
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="about-grid">
    <div class="about-item">
      <div class="about-icon">🔭</div>
      <div>
        <div class="about-label">Currently Working On</div>
        <div class="about-text">Sharpening skills with real-world projects</div>
      </div>
    </div>
    <div class="about-item">
      <div class="about-icon">🌱</div>
      <div>
        <div class="about-label">Currently Learning</div>
        <div class="about-text">Full Stack Dev & Version Control</div>
      </div>
    </div>
    <div class="about-item">
      <div class="about-icon">👯</div>
      <div>
        <div class="about-label">Looking to Collaborate</div>
        <div class="about-text">Beginner-friendly open source projects</div>
      </div>
    </div>
    <div class="about-item">
      <div class="about-icon">🤝</div>
      <div>
        <div class="about-label">Looking for Help With</div>
        <div class="about-text">Data Structures & Algorithms</div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section-label">Tech Stack</div>
  <div class="tech-card">
    <div class="tech-card-header">
      <div class="tech-card-title">Languages & Frameworks</div>
      <div class="tech-badge">17 technologies</div>
    </div>

    <div class="tech-group">
      <div class="tech-group-label">Languages</div>
      <div class="tech-icons">
        <div class="tech-icon">
          <svg viewBox="0 0 32 32" fill="none"><path d="M16 4L4 10v12l12 6 12-6V10L16 4z" fill="#00599C"/><path d="M16 4v24M4 10l12 6 12-6" stroke="#fff" stroke-width="1.5" opacity=".4"/></svg>
          C
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32" fill="none"><path d="M16 4L4 10v12l12 6 12-6V10L16 4z" fill="#00599C"/><text x="9" y="22" font-size="12" fill="white" font-weight="bold">++</text></svg>
          C++
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#F7DF1E"/><text x="6" y="24" font-size="18" font-weight="bold" fill="#323330">JS</text></svg>
          JavaScript
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#3178C6"/><text x="5" y="24" font-size="17" font-weight="bold" fill="white">TS</text></svg>
          TypeScript
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#1e3a5f"/><path d="M16 7c-4.97 0-9 4.03-9 9s4.03 9 9 9 9-4.03 9-9-4.03-9-9-9zm0 4a5 5 0 110 10 5 5 0 010-10z" fill="#60a5fa"/></svg>
          Python
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#1a2580"/><text x="5" y="23" font-size="14" font-weight="bold" fill="white">PHP</text></svg>
          PHP
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#E34F26"/><text x="7" y="23" font-size="14" font-weight="bold" fill="white">H5</text></svg>
          HTML5
        </div>
      </div>
    </div>

    <div class="tech-group">
      <div class="tech-group-label">Frontend</div>
      <div class="tech-icons">
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="16" fill="#0d1b35"/><path d="M16 12a4 4 0 100 8 4 4 0 000-8z" fill="#61DAFB"/><ellipse cx="16" cy="16" rx="12" ry="5" stroke="#61DAFB" stroke-width="1.5" fill="none"/><ellipse cx="16" cy="16" rx="12" ry="5" stroke="#61DAFB" stroke-width="1.5" fill="none" transform="rotate(60 16 16)"/><ellipse cx="16" cy="16" rx="12" ry="5" stroke="#61DAFB" stroke-width="1.5" fill="none" transform="rotate(120 16 16)"/></svg>
          React
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#060a14"/><path d="M8 24V8h7l5 8-5 8H8z" fill="white" opacity=".9"/></svg>
          Next.js
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#0769AD"/><path d="M9 8h14l-7 9v7" stroke="white" stroke-width="2.5" fill="none" stroke-linecap="round" stroke-linejoin="round"/></svg>
          jQuery
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#0f1e50"/><circle cx="16" cy="16" r="7" fill="none" stroke="#60a5fa" stroke-width="2"/><circle cx="16" cy="16" r="3" fill="#60a5fa"/></svg>
          React Router
        </div>
      </div>
    </div>

    <div class="tech-group">
      <div class="tech-group-label">Backend & Runtime</div>
      <div class="tech-icons">
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#0d1f0d"/><path d="M16 6c-5.52 0-10 4.48-10 10s4.48 10 10 10 10-4.48 10-10S21.52 6 16 6zm0 3c.83 0 1.5.67 1.5 1.5v5.17l3.54 3.54-1.06 1.06-3.73-3.73A1.5 1.5 0 0114.5 15V10.5c0-.83.67-1.5 1.5-1.5z" fill="#6DA55F"/></svg>
          Node.js
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#D42029"/><path d="M8 10h5l3 12 3-12h5" stroke="white" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/></svg>
          Apache
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#CB3837"/><circle cx="16" cy="16" r="7" fill="white"/><circle cx="16" cy="16" r="3" fill="#CB3837"/></svg>
          NPM
        </div>
      </div>
    </div>

    <div class="tech-group">
      <div class="tech-group-label">Tools & Platforms</div>
      <div class="tech-icons">
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#0d1117"/><path d="M16 5C9.92 5 5 9.92 5 16c0 4.86 3.15 8.99 7.52 10.44.55.1.75-.24.75-.53v-1.86c-3.06.66-3.7-1.48-3.7-1.48-.5-1.27-1.22-1.61-1.22-1.61-1-.68.07-.67.07-.67 1.1.08 1.68 1.13 1.68 1.13.98 1.68 2.57 1.19 3.2.91.1-.71.38-1.19.7-1.46-2.44-.28-5.01-1.22-5.01-5.44 0-1.2.43-2.18 1.13-2.95-.11-.28-.49-1.4.11-2.91 0 0 .92-.3 3.02 1.13a10.5 10.5 0 012.75-.37c.93 0 1.87.13 2.75.37 2.1-1.43 3.02-1.13 3.02-1.13.6 1.51.22 2.63.11 2.91.7.77 1.13 1.75 1.13 2.95 0 4.23-2.58 5.16-5.03 5.43.4.34.75 1.01.75 2.03v3.01c0 .29.19.64.75.53A11.01 11.01 0 0027 16c0-6.08-4.92-11-11-11z" fill="white"/></svg>
          GitHub
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#F05033"/><path d="M16 5l-2.5 5.5-6 .5 4.5 4-1.5 6 5.5-3.5 5.5 3.5-1.5-6 4.5-4-6-.5z" fill="white"/></svg>
          Git
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#060606"/><polygon points="16,7 26,25 6,25" fill="white" opacity=".95"/></svg>
          Vercel
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#05183d"/><path d="M8 24L16 8l8 16H8z" fill="#60a5fa"/></svg>
          Netlify
        </div>
        <div class="tech-icon">
          <svg viewBox="0 0 32 32"><rect width="32" height="32" rx="4" fill="#0f2a5e"/><text x="5" y="22" font-size="16" font-weight="bold" fill="#93c5fd">Ca</text></svg>
          Canva
        </div>
      </div>
    </div>
  </div>

  <!-- SOCIALS -->
  <div class="section-label">Connect</div>
  <div class="socials-row">
    <a class="social-link" href="https://linkedin.com/in/sakib-sayyad/" target="_blank">
      <svg viewBox="0 0 24 24" fill="#0077B5"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
      LinkedIn
    </a>
    <a class="social-link" href="https://instagram.com/creation__infinity" target="_blank">
      <svg viewBox="0 0 24 24" fill="url(#ig)">
        <defs><linearGradient id="ig" x1="0%" y1="100%" x2="100%" y2="0%"><stop offset="0%" stop-color="#f09433"/><stop offset="50%" stop-color="#dc2743"/><stop offset="100%" stop-color="#bc1888"/></linearGradient></defs>
        <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/>
      </svg>
      Instagram
    </a>
    <a class="social-link" href="https://youtube.com/@SakibSayyad21" target="_blank">
      <svg viewBox="0 0 24 24" fill="#FF0000"><path d="M23.495 6.205a3.007 3.007 0 00-2.088-2.088c-1.87-.501-9.396-.501-9.396-.501s-7.507-.01-9.396.501A3.007 3.007 0 00.527 6.205a31.247 31.247 0 00-.522 5.805 31.247 31.247 0 00.522 5.783 3.007 3.007 0 002.088 2.088c1.868.502 9.396.502 9.396.502s7.506 0 9.396-.502a3.007 3.007 0 002.088-2.088 31.247 31.247 0 00.5-5.783 31.247 31.247 0 00-.5-5.805zM9.609 15.601V8.408l6.264 3.602z"/></svg>
      YouTube
    </a>
    <a class="social-link" href="mailto:sakibsayyad29706@gmail.com">
      <svg viewBox="0 0 24 24" fill="#D14836"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
      Email
    </a>
  </div>

  <!-- STATS -->
  <div class="section-label">Activity</div>
  <div class="stats-row">
    <div class="stat-card">
      <div class="stat-num">17</div>
      <div class="stat-desc">Technologies</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">4+</div>
      <div class="stat-desc">Socials</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">∞</div>
      <div class="stat-desc">Learning</div>
    </div>
  </div>

  <!-- FUN FACT -->
  <div class="fun-fact">
    <div class="fun-fact-icon">⚡</div>
    <div class="fun-fact-text">
      <strong>Fun fact:</strong> My code runs perfectly… until I show it to someone else.
    </div>
  </div>

</div>
</body>
</html>
