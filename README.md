
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bahar TASKIN — SDET Portfolio</title>
  <meta name="description" content="Bahar TASKIN — Software Development Engineer in Test. Java, Selenium, Cucumber, BDD, API Testing."/>

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet"/>

  <style>
    /* ══════════════════════════════════════════
       CSS VARIABLES & RESET
    ══════════════════════════════════════════ */
    :root {
      --green-bright:  #23d96c;
      --green-mid:     #43b02a;
      --green-dark:    #145214;
      --green-deep:    #0a1f0a;
      --green-glow:    #00ff88;
      --green-soft:    #e8ffe8;
      --bg-primary:    #0d1117;
      --bg-secondary:  #161b22;
      --bg-card:       #1a2332;
      --bg-card-hover: #1e2a3a;
      --text-primary:  #e6edf3;
      --text-secondary:#8b949e;
      --text-muted:    #484f58;
      --border:        #30363d;
      --border-green:  rgba(35,217,108,0.3);
      --shadow-green:  0 0 30px rgba(35,217,108,0.15);
      --shadow-card:   0 8px 32px rgba(0,0,0,0.4);
      --radius:        12px;
      --radius-lg:     20px;
      --transition:    all 0.3s cubic-bezier(0.4,0,0.2,1);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--bg-primary);
      color: var(--text-primary);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ══════════════════════════════════════════
       SCROLLBAR
    ══════════════════════════════════════════ */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--bg-primary); }
    ::-webkit-scrollbar-thumb { background: var(--green-dark); border-radius: 3px; }
    ::-webkit-scrollbar-thumb:hover { background: var(--green-mid); }

    /* ══════════════════════════════════════════
       ANIMATED BACKGROUND GRID
    ══════════════════════════════════════════ */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(35,217,108,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(35,217,108,0.03) 1px, transparent 1px);
      background-size: 50px 50px;
      pointer-events: none;
      z-index: 0;
    }

    /* ══════════════════════════════════════════
       PARTICLES CANVAS
    ══════════════════════════════════════════ */
    #particles { position: fixed; inset: 0; pointer-events: none; z-index: 0; }

    /* ══════════════════════════════════════════
       NAV
    ══════════════════════════════════════════ */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 0 5%;
      height: 64px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: rgba(13,17,23,0.85);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border-bottom: 1px solid var(--border-green);
    }

    .nav-logo {
      font-family: 'Fira Code', monospace;
      font-size: 1rem;
      font-weight: 600;
      color: var(--green-bright);
      letter-spacing: 1px;
    }
    .nav-logo span { color: var(--text-secondary); }

    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      font-size: 0.85rem;
      font-weight: 500;
      color: var(--text-secondary);
      text-decoration: none;
      letter-spacing: 0.5px;
      transition: var(--transition);
      position: relative;
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px; left: 0; right: 100%;
      height: 2px;
      background: var(--green-bright);
      transition: var(--transition);
    }
    .nav-links a:hover { color: var(--green-bright); }
    .nav-links a:hover::after { right: 0; }

    /* ══════════════════════════════════════════
       HERO SECTION
    ══════════════════════════════════════════ */
    #hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 80px 5% 60px;
      z-index: 1;
      overflow: hidden;
    }

    /* Animated wave bottom */
    #hero::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0; right: 0;
      height: 120px;
      background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 120'%3E%3Cpath fill='%23161b22' d='M0,60 C360,120 1080,0 1440,60 L1440,120 L0,120 Z'/%3E%3C/svg%3E") center/cover no-repeat;
    }

    .hero-inner {
      max-width: 900px;
      width: 100%;
      text-align: center;
      position: relative;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 16px;
      border: 1px solid var(--border-green);
      border-radius: 999px;
      font-family: 'Fira Code', monospace;
      font-size: 0.78rem;
      color: var(--green-bright);
      background: rgba(35,217,108,0.07);
      margin-bottom: 1.5rem;
      animation: fadeInDown 0.8s ease both;
    }
    .hero-badge .dot {
      width: 8px; height: 8px;
      border-radius: 50%;
      background: var(--green-bright);
      animation: pulse 2s infinite;
    }

    .hero-name {
      font-size: clamp(2.8rem, 7vw, 5.5rem);
      font-weight: 900;
      letter-spacing: -2px;
      line-height: 1.05;
      margin-bottom: 0.4rem;
      animation: fadeInUp 0.9s 0.1s ease both;
    }
    .hero-name .first { color: var(--text-primary); }
    .hero-name .last {
      color: var(--green-bright);
      text-shadow: 0 0 40px rgba(35,217,108,0.5);
    }

    .hero-title {
      font-size: clamp(1rem, 2.5vw, 1.3rem);
      font-weight: 500;
      color: var(--text-secondary);
      margin-bottom: 1.8rem;
      animation: fadeInUp 0.9s 0.2s ease both;
    }
    .hero-title .highlight {
      color: var(--green-bright);
      font-weight: 600;
    }

    /* Typewriter */
    .typewriter-wrap {
      font-family: 'Fira Code', monospace;
      font-size: clamp(0.85rem, 2vw, 1.05rem);
      color: var(--green-mid);
      margin-bottom: 2.5rem;
      min-height: 1.6em;
      animation: fadeInUp 0.9s 0.3s ease both;
    }
    #typewriter { border-right: 2px solid var(--green-bright); padding-right: 3px; }

    .hero-cta {
      display: flex;
      gap: 1rem;
      justify-content: center;
      flex-wrap: wrap;
      animation: fadeInUp 0.9s 0.4s ease both;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 12px 28px;
      border-radius: var(--radius);
      font-size: 0.9rem;
      font-weight: 600;
      text-decoration: none;
      cursor: pointer;
      transition: var(--transition);
      border: 2px solid transparent;
      letter-spacing: 0.3px;
    }
    .btn-primary {
      background: var(--green-bright);
      color: var(--bg-primary);
      border-color: var(--green-bright);
    }
    .btn-primary:hover {
      background: var(--green-glow);
      box-shadow: 0 0 24px rgba(35,217,108,0.5);
      transform: translateY(-2px);
    }
    .btn-outline {
      background: transparent;
      color: var(--green-bright);
      border-color: var(--border-green);
    }
    .btn-outline:hover {
      background: rgba(35,217,108,0.1);
      border-color: var(--green-bright);
      transform: translateY(-2px);
    }

    /* Hero stats */
    .hero-stats {
      display: flex;
      gap: 2.5rem;
      justify-content: center;
      margin-top: 3.5rem;
      padding-top: 2.5rem;
      border-top: 1px solid var(--border);
      animation: fadeInUp 0.9s 0.5s ease both;
    }
    .stat { text-align: center; }
    .stat-num {
      display: block;
      font-size: 2rem;
      font-weight: 900;
      color: var(--green-bright);
      line-height: 1;
    }
    .stat-label {
      font-size: 0.78rem;
      color: var(--text-secondary);
      margin-top: 4px;
      letter-spacing: 0.5px;
    }

    /* ══════════════════════════════════════════
       SECTIONS COMMON
    ══════════════════════════════════════════ */
    section {
      position: relative;
      z-index: 1;
      padding: 80px 5%;
    }

    .section-inner { max-width: 1100px; margin: 0 auto; }

    .section-label {
      font-family: 'Fira Code', monospace;
      font-size: 0.78rem;
      font-weight: 600;
      color: var(--green-bright);
      letter-spacing: 2px;
      text-transform: uppercase;
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 0.75rem;
    }
    .section-label::before {
      content: '//';
      color: var(--text-muted);
    }

    .section-title {
      font-size: clamp(1.8rem, 4vw, 2.6rem);
      font-weight: 800;
      letter-spacing: -1px;
      margin-bottom: 3rem;
      color: var(--text-primary);
    }
    .section-title span { color: var(--green-bright); }

    /* ══════════════════════════════════════════
       ABOUT SECTION
    ══════════════════════════════════════════ */
    #about { background: var(--bg-secondary); }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
      align-items: start;
    }

    .about-text p {
      color: var(--text-secondary);
      margin-bottom: 1.2rem;
      font-size: 0.95rem;
      line-height: 1.8;
    }
    .about-text p strong { color: var(--text-primary); }

    .about-info-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
      margin-top: 1.5rem;
    }
    .info-item {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 10px 14px;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      font-size: 0.85rem;
    }
    .info-item .icon { font-size: 1.1rem; }
    .info-item .label { color: var(--text-muted); font-size: 0.75rem; }
    .info-item .value { color: var(--text-primary); font-weight: 500; font-size: 0.85rem; }

    /* Code card */
    .code-card {
      background: var(--bg-primary);
      border: 1px solid var(--border-green);
      border-radius: var(--radius-lg);
      overflow: hidden;
      box-shadow: var(--shadow-green);
    }
    .code-header {
      display: flex;
      align-items: center;
      gap: 6px;
      padding: 14px 16px;
      background: var(--bg-card);
      border-bottom: 1px solid var(--border);
    }
    .code-dot {
      width: 12px; height: 12px;
      border-radius: 50%;
    }
    .dot-red    { background: #ff5f56; }
    .dot-yellow { background: #ffbd2e; }
    .dot-green  { background: #27c93f; }
    .code-filename {
      font-family: 'Fira Code', monospace;
      font-size: 0.78rem;
      color: var(--text-secondary);
      margin-left: 8px;
    }
    .code-body {
      padding: 1.5rem;
      font-family: 'Fira Code', monospace;
      font-size: 0.82rem;
      line-height: 1.9;
      overflow-x: auto;
    }
    .c-keyword  { color: #ff7b72; }
    .c-class    { color: #ffa657; }
    .c-string   { color: #a5d6ff; }
    .c-comment  { color: #8b949e; }
    .c-var      { color: #79c0ff; }
    .c-green    { color: var(--green-bright); }
    .c-punct    { color: var(--text-secondary); }
    .indent     { padding-left: 1.5rem; }
    .indent2    { padding-left: 3rem; }

    /* ══════════════════════════════════════════
       SKILLS SECTION
    ══════════════════════════════════════════ */
    #skills { background: var(--bg-primary); }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 1.5rem;
    }

    .skill-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      padding: 1.8rem;
      transition: var(--transition);
    }
    .skill-card:hover {
      border-color: var(--border-green);
      box-shadow: var(--shadow-green);
      transform: translateY(-4px);
      background: var(--bg-card-hover);
    }
    .skill-card-icon {
      font-size: 2rem;
      margin-bottom: 1rem;
    }
    .skill-card-title {
      font-size: 1rem;
      font-weight: 700;
      color: var(--text-primary);
      margin-bottom: 1rem;
    }
    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }
    .tag {
      display: inline-block;
      padding: 4px 10px;
      border-radius: 6px;
      font-size: 0.75rem;
      font-weight: 600;
      font-family: 'Fira Code', monospace;
      background: rgba(35,217,108,0.1);
      color: var(--green-bright);
      border: 1px solid rgba(35,217,108,0.2);
      transition: var(--transition);
    }
    .tag:hover {
      background: rgba(35,217,108,0.2);
      border-color: var(--green-bright);
    }
    .tag.blue   { background: rgba(79,148,255,0.1);  color: #79c0ff; border-color: rgba(79,148,255,0.2); }
    .tag.orange { background: rgba(255,166,87,0.1);  color: #ffa657; border-color: rgba(255,166,87,0.2); }
    .tag.purple { background: rgba(188,140,255,0.1); color: #d2a8ff; border-color: rgba(188,140,255,0.2); }
    .tag.red    { background: rgba(255,123,114,0.1); color: #ff7b72; border-color: rgba(255,123,114,0.2); }

    /* Skill bars */
    .skill-bar-group { margin-top: 1rem; }
    .skill-bar-item  { margin-bottom: 1rem; }
    .skill-bar-top {
      display: flex;
      justify-content: space-between;
      margin-bottom: 6px;
      font-size: 0.82rem;
    }
    .skill-bar-name  { color: var(--text-primary); font-weight: 500; }
    .skill-bar-pct   { color: var(--green-bright); font-family: 'Fira Code', monospace; }
    .skill-bar-track {
      height: 6px;
      background: var(--border);
      border-radius: 3px;
      overflow: hidden;
    }
    .skill-bar-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--green-dark), var(--green-bright));
      border-radius: 3px;
      width: 0;
      transition: width 1.2s cubic-bezier(0.4,0,0.2,1);
    }

    /* ══════════════════════════════════════════
       EXPERIENCE SECTION
    ══════════════════════════════════════════ */
    #experience { background: var(--bg-secondary); }

    .timeline { position: relative; padding-left: 2rem; }
    .timeline::before {
      content: '';
      position: absolute;
      left: 0; top: 12px; bottom: 0;
      width: 2px;
      background: linear-gradient(to bottom, var(--green-bright), transparent);
    }

    .timeline-item {
      position: relative;
      margin-bottom: 2.5rem;
    }
    .timeline-dot {
      position: absolute;
      left: -2rem;
      top: 12px;
      width: 14px; height: 14px;
      border-radius: 50%;
      background: var(--green-bright);
      border: 3px solid var(--bg-secondary);
      box-shadow: 0 0 12px rgba(35,217,108,0.6);
      transform: translateX(-6px);
    }

    .exp-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      padding: 2rem;
      transition: var(--transition);
    }
    .exp-card:hover {
      border-color: var(--border-green);
      box-shadow: var(--shadow-green);
    }
    .exp-top {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 0.5rem;
    }
    .exp-company {
      font-size: 1.2rem;
      font-weight: 800;
      color: var(--green-bright);
    }
    .exp-date {
      font-family: 'Fira Code', monospace;
      font-size: 0.78rem;
      color: var(--text-muted);
      padding: 4px 12px;
      border: 1px solid var(--border);
      border-radius: 999px;
      white-space: nowrap;
    }
    .exp-role {
      font-size: 1rem;
      font-weight: 600;
      color: var(--text-primary);
      margin-bottom: 0.3rem;
    }
    .exp-project {
      font-size: 0.85rem;
      color: var(--text-secondary);
      margin-bottom: 1.2rem;
      font-style: italic;
    }
    .exp-bullets { list-style: none; }
    .exp-bullets li {
      position: relative;
      padding-left: 1.4rem;
      margin-bottom: 0.6rem;
      font-size: 0.88rem;
      color: var(--text-secondary);
      line-height: 1.7;
    }
    .exp-bullets li::before {
      content: '▸';
      position: absolute;
      left: 0;
      color: var(--green-bright);
    }
    .exp-bullets li strong { color: var(--text-primary); }

    .exp-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 1.2rem;
    }

    /* ══════════════════════════════════════════
       FRAMEWORKS SECTION
    ══════════════════════════════════════════ */
    #frameworks { background: var(--bg-primary); }

    .fw-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.2rem;
    }

    .fw-card {
      display: flex;
      gap: 1.2rem;
      align-items: flex-start;
      padding: 1.5rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      transition: var(--transition);
    }
    .fw-card:hover {
      border-color: var(--border-green);
      transform: translateX(4px);
      box-shadow: var(--shadow-green);
    }
    .fw-icon {
      font-size: 1.8rem;
      min-width: 40px;
      text-align: center;
    }
    .fw-title {
      font-size: 0.95rem;
      font-weight: 700;
      color: var(--text-primary);
      margin-bottom: 0.35rem;
    }
    .fw-desc {
      font-size: 0.82rem;
      color: var(--text-secondary);
      line-height: 1.6;
    }

    /* ══════════════════════════════════════════
       EDUCATION SECTION
    ══════════════════════════════════════════ */
    #education { background: var(--bg-secondary); }

    .edu-card {
      background: var(--bg-card);
      border: 1px solid var(--border-green);
      border-radius: var(--radius-lg);
      padding: 2rem 2.5rem;
      display: flex;
      gap: 2rem;
      align-items: center;
      box-shadow: var(--shadow-green);
      max-width: 680px;
    }
    .edu-icon { font-size: 3.5rem; }
    .edu-degree {
      font-size: 1.2rem;
      font-weight: 800;
      color: var(--text-primary);
      margin-bottom: 0.3rem;
    }
    .edu-school {
      font-size: 1rem;
      font-weight: 600;
      color: var(--green-bright);
      margin-bottom: 0.3rem;
    }
    .edu-detail {
      font-size: 0.85rem;
      color: var(--text-secondary);
    }

    /* ══════════════════════════════════════════
       CONTACT SECTION
    ══════════════════════════════════════════ */
    #contact { background: var(--bg-primary); text-align: center; }

    .contact-subtitle {
      color: var(--text-secondary);
      font-size: 1rem;
      max-width: 480px;
      margin: -1.5rem auto 2.5rem;
      line-height: 1.7;
    }

    .contact-cards {
      display: flex;
      gap: 1.2rem;
      justify-content: center;
      flex-wrap: wrap;
      margin-bottom: 3rem;
    }
    .contact-card {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 1.2rem 2rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      text-decoration: none;
      transition: var(--transition);
      min-width: 220px;
    }
    .contact-card:hover {
      border-color: var(--green-bright);
      box-shadow: var(--shadow-green);
      transform: translateY(-4px);
    }
    .contact-card-icon { font-size: 1.8rem; }
    .contact-card-label { font-size: 0.75rem; color: var(--text-muted); }
    .contact-card-value { font-size: 0.9rem; font-weight: 600; color: var(--text-primary); }

    /* ══════════════════════════════════════════
       FOOTER
    ══════════════════════════════════════════ */
    footer {
      position: relative;
      z-index: 1;
      background: var(--bg-secondary);
      border-top: 1px solid var(--border);
      padding: 2rem 5%;
      text-align: center;
      font-size: 0.82rem;
      color: var(--text-muted);
    }
    footer span { color: var(--green-bright); }

    /* ══════════════════════════════════════════
       ANIMATIONS
    ══════════════════════════════════════════ */
    @keyframes fadeInDown {
      from { opacity: 0; transform: translateY(-20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50%       { opacity: 0.5; transform: scale(0.8); }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50%       { transform: translateY(-8px); }
    }

    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ══════════════════════════════════════════
       RESPONSIVE
    ══════════════════════════════════════════ */
    @media (max-width: 768px) {
      nav { padding: 0 4%; }
      .nav-links { gap: 1.2rem; }
      .nav-links a { font-size: 0.78rem; }
      .about-grid { grid-template-columns: 1fr; }
      .about-info-grid { grid-template-columns: 1fr; }
      .hero-stats { gap: 1.5rem; }
      .edu-card { flex-direction: column; text-align: center; }
      .exp-top { flex-direction: column; }
      section { padding: 60px 4%; }
    }
    @media (max-width: 480px) {
      .nav-links { display: none; }
      .hero-cta { flex-direction: column; align-items: center; }
      .contact-card { min-width: 100%; }
    }
  </style>
</head>

<body>

  <!-- Particles -->
  <canvas id="particles"></canvas>

  <!-- ════════════════════════ NAV ════════════════════════ -->
  <nav>
    <div class="nav-logo">&lt;<span>BaharTaskin</span> /&gt;</div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#frameworks">Frameworks</a></li>
      <li><a href="#education">Education</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- ════════════════════════ HERO ════════════════════════ -->
  <section id="hero">
    <div class="hero-inner">
      <div class="hero-badge">
        <span class="dot"></span>
        Available for new opportunities
      </div>

      <h1 class="hero-name">
        <span class="first">Bahar </span><span class="last">TASKIN</span>
      </h1>

      <p class="hero-title">
        <span class="highlight">Software Development Engineer in Test</span>
        &nbsp;·&nbsp; Ankara, Turkey 🇹🇷
      </p>

      <div class="typewriter-wrap">
        &gt; <span id="typewriter"></span>
      </div>

      <div class="hero-cta">
        <a href="#experience" class="btn btn-primary">💼 View Experience</a>
        <a href="#contact"    class="btn btn-outline">📬 Get In Touch</a>
        <a href="/cdn-cgi/l/email-protection#1576747e7c67777d6722557278747c793b767a78" class="btn btn-outline">✉️ <span class="__cf_email__" data-cfemail="afcccec4c6ddcdc7dd98efc8c2cec6c381ccc0c2">[email&#160;protected]</span></a>
      </div>

      <div class="hero-stats">
        <div class="stat">
          <span class="stat-num">3+</span>
          <span class="stat-label">Years Experience</span>
        </div>
        <div class="stat">
          <span class="stat-num">10+</span>
          <span class="stat-label">Tools & Frameworks</span>
        </div>
        <div class="stat">
          <span class="stat-num">100%</span>
          <span class="stat-label">Quality Focused</span>
        </div>
        <div class="stat">
          <span class="stat-num">METU</span>
          <span class="stat-label">Graduate</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ════════════════════════ ABOUT ════════════════════════ -->
  <section id="about">
    <div class="section-inner">
      <div class="section-label">About Me</div>
      <h2 class="section-title">Passionate about <span>Quality</span></h2>

      <div class="about-grid">
        <div class="about-text reveal">
          <p>
            I'm a <strong>Software Development Engineer in Test (SDET)</strong> with hands-on experience in both manual and automated testing for web-based applications across the full Software Development Life Cycle.
          </p>
          <p>
            I specialize in building robust <strong>test automation frameworks</strong> from scratch using Java, Selenium WebDriver, Cucumber BDD, Rest Assured, and JUnit — integrating UI, API, and Database layers in a single unified framework.
          </p>
          <p>
            I thrive in <strong>Agile/Scrum</strong> environments, actively participating in Sprint Planning, Grooming, Daily Standups, Demos, and Retrospectives. I believe clean, maintainable test code is living documentation for any product.
          </p>
          <p>
            Always learning, always improving — dedicated to growing skills and delivering high-quality software every day. 🐛
          </p>

          <div class="about-info-grid">
            <div class="info-item">
              <span class="icon">📍</span>
              <div><div class="label">Location</div><div class="value">Ankara, Turkey</div></div>
            </div>
            <div class="info-item">
              <span class="icon">✉️</span>
              <div><div class="label">Email</div><div class="value"><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="8deeece6e4ffefe5ffbacdeae0ece4e1a3eee2e0">[email&#160;protected]</a></div></div>
            </div>
            <div class="info-item">
              <span class="icon">📞</span>
              <div><div class="label">Phone</div><div class="value">+90 530-124-55-14</div></div>
            </div>
            <div class="info-item">
              <span class="icon">🎓</span>
              <div><div class="label">University</div><div class="value">METU, Ankara</div></div>
            </div>
          </div>
        </div>

        <!-- Code Card -->
        <div class="code-card reveal" style="transition-delay:0.2s">
          <div class="code-header">
            <div class="code-dot dot-red"></div>
            <div class="code-dot dot-yellow"></div>
            <div class="code-dot dot-green"></div>
            <span class="code-filename">BaharTaskin.java</span>
          </div>
          <div class="code-body">
            <div><span class="c-keyword">public class</span> <span class="c-class">BaharTaskin</span> <span class="c-punct">{</span></div>
            <br/>
            <div class="indent"><span class="c-var">String</span> name <span class="c-punct">=</span> <span class="c-string">"Bahar TASKIN"</span><span class="c-punct">;</span></div>
            <div class="indent"><span class="c-var">String</span> role <span class="c-punct">=</span> <span class="c-string">"SDET"</span><span class="c-punct">;</span></div>
            <div class="indent"><span class="c-var">String</span> city <span class="c-punct">=</span> <span class="c-string">"Ankara 🇹🇷"</span><span class="c-punct">;</span></div>
            <br/>
            <div class="indent"><span class="c-comment">// Core skills</span></div>
            <div class="indent"><span class="c-var">String[]</span> stack <span class="c-punct">= {</span></div>
            <div class="indent2"><span class="c-string">"Java"</span><span class="c-punct">,</span> <span class="c-string">"Selenium"</span><span class="c-punct">,</span></div>
            <div class="indent2"><span class="c-string">"Cucumber"</span><span class="c-punct">,</span> <span class="c-string">"JUnit"</span><span class="c-punct">,</span></div>
            <div class="indent2"><span class="c-string">"Rest Assured"</span><span class="c-punct">,</span> <span class="c-string">"Maven"</span><span class="c-punct">,</span></div>
            <div class="indent2"><span class="c-string">"Jenkins"</span><span class="c-punct">,</span> <span class="c-string">"SQL"</span></div>
            <div class="indent"><span class="c-punct">};</span></div>
            <br/>
            <div class="indent"><span class="c-var">String</span> motto <span class="c-punct">=</span></div>
            <div class="indent2"><span class="c-string">"Breaking bugs before"</span></div>
            <div class="indent2"><span class="c-string">"users do 🐛"</span><span class="c-punct">;</span></div>
            <br/>
            <div><span class="c-punct">}</span></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ════════════════════════ SKILLS ════════════════════════ -->
  <section id="skills">
    <div class="section-inner">
      <div class="section-label">Tech Stack</div>
      <h2 class="section-title">Skills &amp; <span>Tools</span></h2>

      <div class="skills-grid">

        <!-- Testing Tools -->
        <div class="skill-card reveal">
          <div class="skill-card-icon">🧪</div>
          <div class="skill-card-title">Testing Tools</div>
          <div class="skill-tags">
            <span class="tag">Selenium WebDriver</span>
            <span class="tag">Cucumber</span>
            <span class="tag">Rest Assured</span>
            <span class="tag">Postman</span>
            <span class="tag">JUnit</span>
            <span class="tag">TestNG</span>
            <span class="tag">Apache POI</span>
            <span class="tag">Hamcrest</span>
            <span class="tag">Lombok</span>
            <span class="tag">Serenity</span>
          </div>
        </div>

        <!-- Languages -->
        <div class="skill-card reveal" style="transition-delay:0.1s">
          <div class="skill-card-icon">☕</div>
          <div class="skill-card-title">Languages</div>
          <div class="skill-tags">
            <span class="tag orange">Java</span>
            <span class="tag blue">SQL</span>
            <span class="tag">Gherkin</span>
            <span class="tag blue">HTML</span>
          </div>
          <div class="skill-bar-group" style="margin-top:1.5rem">
            <div class="skill-bar-item">
              <div class="skill-bar-top"><span class="skill-bar-name">Java</span><span class="skill-bar-pct">90%</span></div>
              <div class="skill-bar-track"><div class="skill-bar-fill" data-width="90"></div></div>
            </div>
            <div class="skill-bar-item">
              <div class="skill-bar-top"><span class="skill-bar-name">SQL</span><span class="skill-bar-pct">80%</span></div>
              <div class="skill-bar-track"><div class="skill-bar-fill" data-width="80"></div></div>
            </div>
            <div class="skill-bar-item">
              <div class="skill-bar-top"><span class="skill-bar-name">Gherkin / BDD</span><span class="skill-bar-pct">85%</span></div>
              <div class="skill-bar-track"><div class="skill-bar-fill" data-width="85"></div></div>
            </div>
          </div>
        </div>

        <!-- Build & CI/CD -->
        <div class="skill-card reveal" style="transition-delay:0.2s">
          <div class="skill-card-icon">⚙️</div>
          <div class="skill-card-title">Build &amp; CI/CD</div>
          <div class="skill-tags">
            <span class="tag red">Maven</span>
            <span class="tag orange">Jenkins</span>
            <span class="tag purple">Git</span>
            <span class="tag purple">GitHub</span>
          </div>
          <div class="skill-bar-group" style="margin-top:1.5rem">
            <div class="skill-bar-item">
              <div class="skill-bar-top"><span class="skill-bar-name">Maven</span><span class="skill-bar-pct">85%</span></div>
              <div class="skill-bar-track"><div class="skill-bar-fill" data-width="85"></div></div>
            </div>
            <div class="skill-bar-item">
              <div class="skill-bar-top"><span class="skill-bar-name">Jenkins</span><span class="skill-bar-pct">80%</span></div>
              <div class="skill-bar-track"><div class="skill-bar-fill" data-width="80"></div></div>
            </div>
            <div class="skill-bar-item">
              <div class="skill-bar-top"><span class="skill-bar-name">Git / GitHub</span><span class="skill-bar-pct">88%</span></div>
              <div class="skill-bar-track"><div class="skill-bar-fill" data-width="88"></div></div>
            </div>
          </div>
        </div>

        <!-- Databases & Tools -->
        <div class="skill-card reveal" style="transition-delay:0.3s">
          <div class="skill-card-icon">🗃️</div>
          <div class="skill-card-title">Databases &amp; Management</div>
          <div class="skill-tags">
            <span class="tag red">Oracle</span>
            <span class="tag blue">MySQL</span>
            <span class="tag orange">Jira</span>
            <span class="tag">TestRail</span>
            <span class="tag purple">IntelliJ IDEA</span>
            <span class="tag">SQL Developer</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ════════════════════════ EXPERIENCE ════════════════════════ -->
  <section id="experience">
    <div class="section-inner">
      <div class="section-label">Work History</div>
      <h2 class="section-title">Work <span>Experience</span></h2>

      <div class="timeline">
        <div class="timeline-item reveal">
          <div class="timeline-dot"></div>
          <div class="exp-card">
            <div class="exp-top">
              <div>
                <div class="exp-company">🏢 CYDEO</div>
                <div class="exp-role">Software Development Engineer in Test</div>
                <div class="exp-project">📁 Project: OpenCRM Web-Based Application</div>
              </div>
              <div class="exp-date">📅 Sep 2022 – Present</div>
            </div>

            <ul class="exp-bullets">
              <li>Participated in <strong>Grooming, Daily Scrum, Demo and Retro</strong> meetings every sprint</li>
              <li>Ran daily <strong>Smoke Tests</strong> via Jenkins CI pipeline integration with GitHub</li>
              <li>Executed full <strong>Regression Test</strong> suites after every sprint completion</li>
              <li>Wrote detailed <strong>Test Cases</strong> with Positive &amp; Negative scenarios based on Test Plans</li>
              <li>Managed test cases and bug reports using <strong>Jira</strong> and <strong>TestRail</strong></li>
              <li>Performed both <strong>manual and automated</strong> testing across all feature deliverables</li>
              <li>Wrote complex <strong>SQL queries</strong> for backend database validation using JDBC</li>
              <li>Used <strong>Postman</strong> and <strong>Rest Assured + Serenity + JUnit</strong> for API testing</li>
              <li>Asserted UI behavior via <strong>Cucumber BDD</strong> with JUnit &amp; Selenium WebDriver</li>
              <li>Performed <strong>UI ↔ DB cross-validation</strong> in a unified Cucumber BDD framework</li>
              <li>Generated and shared <strong>Cucumber HTML Reports</strong> for automated test results</li>
            </ul>

            <div class="exp-tags">
              <span class="tag">Java</span>
              <span class="tag">Selenium WebDriver</span>
              <span class="tag">Cucumber BDD</span>
              <span class="tag">JUnit</span>
              <span class="tag orange">Rest Assured</span>
              <span class="tag blue">SQL / JDBC</span>
              <span class="tag red">Jenkins</span>
              <span class="tag purple">GitHub</span>
              <span class="tag orange">Jira</span>
              <span class="tag">TestRail</span>
              <span class="tag blue">Postman</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ════════════════════════ FRAMEWORKS ════════════════════════ -->
  <section id="frameworks">
    <div class="section-inner">
      <div class="section-label">Methodologies</div>
      <h2 class="section-title">Frameworks &amp; <span>Methodologies</span></h2>

      <div class="fw-grid">
        <div class="fw-card reveal">
          <div class="fw-icon">🥒</div>
          <div>
            <div class="fw-title">BDD — Cucumber</div>
            <div class="fw-desc">Human-readable Gherkin scenarios connected to Selenium WebDriver step definitions for end-to-end UI testing.</div>
          </div>
        </div>
        <div class="fw-card reveal" style="transition-delay:0.1s">
          <div class="fw-icon">📄</div>
          <div>
            <div class="fw-title">Page Object Model (POM)</div>
            <div class="fw-desc">Structured UI automation layer with reusable, maintainable page classes separating test logic from UI locators.</div>
          </div>
        </div>
        <div class="fw-card reveal" style="transition-delay:0.2s">
          <div class="fw-icon">📊</div>
          <div>
            <div class="fw-title">Data-Driven Testing</div>
            <div class="fw-desc">Parameterized test execution using Apache POI to read test data from external Excel sources.</div>
          </div>
        </div>
        <div class="fw-card reveal" style="transition-delay:0.3s">
          <div class="fw-icon">🔀</div>
          <div>
            <div class="fw-title">Hybrid Framework</div>
            <div class="fw-desc">POM + Data-Driven combined for maximum test coverage, scalability, and reusability across large suites.</div>
          </div>
        </div>
        <div class="fw-card reveal" style="transition-delay:0.4s">
          <div class="fw-icon">📡</div>
          <div>
            <div class="fw-title">REST API Testing</div>
            <div class="fw-desc">End-to-end API validation with Rest Assured + Serenity libraries, covering CRUD operations with full assertions.</div>
          </div>
        </div>
        <div class="fw-card reveal" style="transition-delay:0.5s">
          <div class="fw-icon">🗄️</div>
          <div>
            <div class="fw-title">Database Testing</div>
            <div class="fw-desc">Backend cross-validation via JDBC + complex SQL queries, ensuring UI data matches database records.</div>
          </div>
        </div>
        <div class="fw-card reveal" style="transition-delay:0.6s">
          <div class="fw-icon">⚡</div>
          <div>
            <div class="fw-title">Agile / Scrum</div>
            <div class="fw-desc">Sprint ceremonies, daily standups, planning and retrospectives in fast-paced delivery teams.</div>
          </div>
        </div>
        <div class="fw-card reveal" style="transition-delay:0.7s">
          <div class="fw-icon">🔁</div>
          <div>
            <div class="fw-title">CI/CD Pipeline</div>
            <div class="fw-desc">GitHub-integrated Jenkins pipelines for daily smoke runs and post-sprint regression execution with Cucumber reports.</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ════════════════════════ EDUCATION ════════════════════════ -->
  <section id="education">
    <div class="section-inner">
      <div class="section-label">Academic Background</div>
      <h2 class="section-title">Education</h2>

      <div class="edu-card reveal">
        <div class="edu-icon">🏛️</div>
        <div>
          <div class="edu-degree">Bachelor's Degree</div>
          <div class="edu-school">Middle East Technical University (METU)</div>
          <div class="edu-detail">📍 Ankara, Turkey &nbsp;·&nbsp; 📅 2008 – 2013</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ════════════════════════ CONTACT ════════════════════════ -->
  <section id="contact">
    <div class="section-inner">
      <div class="section-label" style="justify-content:center">Contact</div>
      <h2 class="section-title" style="text-align:center">Let's <span>Connect</span></h2>
      <p class="contact-subtitle">
        Open to new opportunities, collaborations, and conversations about test automation. Feel free to reach out!
      </p>

      <div class="contact-cards">
        <a href="/cdn-cgi/l/email-protection#9cfffdf7f5eefef4eeabdcfbf1fdf5f0b2fff3f1" class="contact-card reveal">
          <div class="contact-card-icon">✉️</div>
          <div>
            <div class="contact-card-label">Email</div>
            <div class="contact-card-value"><span class="__cf_email__" data-cfemail="6d0e0c06041f0f051f5a2d0a000c0401430e0200">[email&#160;protected]</span></div>
          </div>
        </a>
        <a href="tel:+905301245514" class="contact-card reveal" style="transition-delay:0.1s">
          <div class="contact-card-icon">📞</div>
          <div>
            <div class="contact-card-label">Phone</div>
            <div class="contact-card-value">+90 530-124-55-14</div>
          </div>
        </a>
        <a href="https://www.linkedin.com/in/bahar-taskin/" target="_blank" class="contact-card reveal" style="transition-delay:0.2s">
          <div class="contact-card-icon">💼</div>
          <div>
            <div class="contact-card-label">LinkedIn</div>
            <div class="contact-card-value">bahar-taskin</div>
          </div>
        </a>
        <a href="https://github.com/BaharTaskin" target="_blank" class="contact-card reveal" style="transition-delay:0.3s">
          <div class="contact-card-icon">🐙</div>
          <div>
            <div class="contact-card-label">GitHub</div>
            <div class="contact-card-value">BaharTaskin</div>
          </div>
        </a>
      </div>

      <div class="reveal" style="transition-delay:0.4s">
        <a href="/cdn-cgi/l/email-protection#6704060c0e15050f155027000a060e0b4904080a" class="btn btn-primary" style="font-size:1rem; padding:14px 40px">
          🐛 Let's Squash Some Bugs Together!
        </a>
      </div>
    </div>
  </section>

  <!-- ════════════════════════ FOOTER ════════════════════════ -->
  <footer>
    <p>
      Designed &amp; built by <span>Bahar TASKIN</span> &nbsp;·&nbsp;
      <span>Software Development Engineer in Test</span> &nbsp;·&nbsp;
      Ankara, Turkey 🇹🇷
    </p>
    <p style="margin-top:6px; font-size:0.75rem;">
      🐛 "Quality is not an act, it is a habit." — Aristotle
    </p>
  </footer>

  <!-- ════════════════════════ JAVASCRIPT ════════════════════════ -->
  <script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
    // ──────────────────────────────────────
    // 1. PARTICLES
    // ──────────────────────────────────────
    (function() {
      const canvas = document.getElementById('particles');
      const ctx    = canvas.getContext('2d');
      let W, H, particles = [];

      function resize() {
        W = canvas.width  = window.innerWidth;
        H = canvas.height = window.innerHeight;
      }
      resize();
      window.addEventListener('resize', resize);

      function Particle() {
        this.x    = Math.random() * W;
        this.y    = Math.random() * H;
        this.vx   = (Math.random() - 0.5) * 0.4;
        this.vy   = (Math.random() - 0.5) * 0.4;
        this.r    = Math.random() * 2 + 0.5;
        this.a    = Math.random() * 0.6 + 0.1;
        const greens = ['#23d96c','#43b02a','#00ff88','#145214','#39d353'];
        this.color = greens[Math.floor(Math.random() * greens.length)];
      }
      Particle.prototype.update = function() {
        this.x += this.vx;
        this.y += this.vy;
        if (this.x < 0) this.x = W;
        if (this.x > W) this.x = 0;
        if (this.y < 0) this.y = H;
        if (this.y > H) this.y = 0;
      };

      for (let i = 0; i < 80; i++) particles.push(new Particle());

      function draw() {
        ctx.clearRect(0, 0, W, H);
        particles.forEach(p => {
          ctx.beginPath();
          ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
          ctx.fillStyle = p.color;
          ctx.globalAlpha = p.a;
          ctx.fill();
          p.update();
        });
        // connections
        ctx.globalAlpha = 1;
        for (let i = 0; i < particles.length; i++) {
          for (let j = i + 1; j < particles.length; j++) {
            const dx = particles[i].x - particles[j].x;
            const dy = particles[i].y - particles[j].y;
            const dist = Math.sqrt(dx*dx + dy*dy);
            if (dist < 120) {
              ctx.beginPath();
              ctx.moveTo(particles[i].x, particles[i].y);
              ctx.lineTo(particles[j].x, particles[j].y);
              ctx.strokeStyle = '#23d96c';
              ctx.globalAlpha = (1 - dist/120) * 0.12;
              ctx.lineWidth = 0.8;
              ctx.stroke();
            }
          }
        }
        ctx.globalAlpha = 1;
        requestAnimationFrame(draw);
      }
      draw();
    })();

    // ──────────────────────────────────────
    // 2. TYPEWRITER
    // ──────────────────────────────────────
    (function() {
      const el    = document.getElementById('typewriter');
      const lines = [
        'Breaking bugs before users do 🐛',
        'Selenium WebDriver + Cucumber BDD',
        'Java | JUnit | Maven | Jenkins',
        'API Testing with Rest Assured 📡',
        'CI/CD | GitHub Actions | Agile ⚡',
        'SQL queries for backend validation 🗃️'
      ];
      let li = 0, ci = 0, deleting = false;

      function type() {
        const line = lines[li];
        if (!deleting) {
          el.textContent = line.slice(0, ++ci);
          if (ci === line.length) { deleting = true; return setTimeout(type, 1800); }
          setTimeout(type, 55);
        } else {
          el.textContent = line.slice(0, --ci);
          if (ci === 0) { deleting = false; li = (li + 1) % lines.length; return setTimeout(type, 400); }
          setTimeout(type, 28);
        }
      }
      setTimeout(type, 800);
    })();

    // ──────────────────────────────────────
    // 3. SCROLL REVEAL
    // ──────────────────────────────────────
    (function() {
      const els = document.querySelectorAll('.reveal');
      const obs = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); }
        });
      }, { threshold: 0.12 });
      els.forEach(el => obs.observe(el));
    })();

    // ──────────────────────────────────────
    // 4. SKILL BARS ANIMATION
    // ──────────────────────────────────────
    (function() {
      const fills = document.querySelectorAll('.skill-bar-fill');
      const obs   = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          if (e.isIntersecting) {
            e.target.style.width = e.target.dataset.width + '%';
            obs.unobserve(e.target);
          }
        });
      }, { threshold: 0.3 });
      fills.forEach(f => obs.observe(f));
    })();

    // ──────────────────────────────────────
    // 5. ACTIVE NAV HIGHLIGHT
    // ──────────────────────────────────────
    (function() {
      const sections = document.querySelectorAll('section[id]');
      const links    = document.querySelectorAll('.nav-links a');
      const obs = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          if (e.isIntersecting) {
            links.forEach(a => a.style.color = '');
            const active = document.querySelector(`.nav-links a[href="#${e.target.id}"]`);
            if (active) active.style.color = '#23d96c';
          }
        });
      }, { threshold: 0.5 });
      sections.forEach(s => obs.observe(s));
    })();
  </script>

</body>
</html>
