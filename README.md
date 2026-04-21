<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Miraj Ud Din AI Engineer & Researcher</title>

  <!-- Favicon -->
  <link rel="icon" type="image/png" href="favicon.png" />

  <!-- ═══════════════════════════════════════════════════════════
       FONTS  – Syne (headings) + DM Sans (body)
  ═══════════════════════════════════════════════════════════ -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,300&display=swap" rel="stylesheet" />

  <!-- ═══════════════════════════════════════════════════════════
       ICONS – Font Awesome 6
  ═══════════════════════════════════════════════════════════ -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" />

  <!-- ═══════════════════════════════════════════════════════════
       DEVICONS (language / tool logos)
  ═══════════════════════════════════════════════════════════ -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.15.1/devicon.min.css" />

  <style>
    /* ══════════════════════════════════════════════════
       1. CSS CUSTOM PROPERTIES (light / dark tokens)
    ══════════════════════════════════════════════════ */
    :root {
      /* Brand palette */
      --accent-1: #00f5c4;   /* teal‑mint */
      --accent-2: #7b5ea7;   /* violet */
      --accent-3: #ff6b6b;   /* coral */
      --accent-4: #ffd166;   /* amber */

      /* Shared */
      --radius-sm: 8px;
      --radius-md: 16px;
      --radius-lg: 28px;
      --transition: 0.35s cubic-bezier(0.4, 0, 0.2, 1);
      --shadow-card: 0 8px 40px rgba(0,0,0,0.18);
      --shadow-card-hover: 0 20px 60px rgba(0,0,0,0.32);
      --font-head: 'Syne', sans-serif;
      --font-body: 'DM Sans', sans-serif;
    }

    /* ── DARK theme (default) ── */
    [data-theme="dark"] {
      --bg-root:   #09090f;
      --bg-panel:  #111118;
      --bg-card:   #16161e;
      --bg-glass:  rgba(22,22,30,0.75);
      --border:    rgba(255,255,255,0.07);
      --text-main: #f0f0f8;
      --text-sub:  #8a8a9e;
      --text-muted:#555568;
      --nav-bg:    rgba(9,9,15,0.85);
      --skill-bar: rgba(255,255,255,0.08);
      --tag-bg:    rgba(0,245,196,0.1);
      --tag-color: var(--accent-1);
    }

    /* ── LIGHT theme ── */
    [data-theme="light"] {
      --bg-root:   #f4f4fa;
      --bg-panel:  #ffffff;
      --bg-card:   #ffffff;
      --bg-glass:  rgba(255,255,255,0.85);
      --border:    rgba(0,0,0,0.07);
      --text-main: #0f0f18;
      --text-sub:  #555568;
      --text-muted:#9999b0;
      --nav-bg:    rgba(244,244,250,0.88);
      --skill-bar: rgba(0,0,0,0.07);
      --tag-bg:    rgba(0,180,145,0.1);
      --tag-color: #00a688;
    }

    /* ══════════════════════════════════════════════════
       2. RESET & BASE
    ══════════════════════════════════════════════════ */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; font-size: 16px; }
    body {
      background: var(--bg-root);
      color: var(--text-main);
      font-family: var(--font-body);
      line-height: 1.65;
      overflow-x: hidden;
      cursor: none; /* custom cursor */
      transition: background var(--transition), color var(--transition);
    }
    a { color: inherit; text-decoration: none; }
    img { display: block; width: 100%; }
    ul { list-style: none; }
    button { cursor: none; font-family: inherit; }

    /* ══════════════════════════════════════════════════
       3. CUSTOM CURSOR
    ══════════════════════════════════════════════════ */
    #cursor-dot {
      position: fixed; top: 0; left: 0; z-index: 99999;
      width: 10px; height: 10px;
      background: var(--accent-1);
      border-radius: 50%;
      pointer-events: none;
      transform: translate(-50%,-50%);
      transition: width 0.2s, height 0.2s, background 0.2s;
      will-change: transform;
    }
    #cursor-ring {
      position: fixed; top: 0; left: 0; z-index: 99998;
      width: 36px; height: 36px;
      border: 2px solid var(--accent-1);
      border-radius: 50%;
      pointer-events: none;
      transform: translate(-50%,-50%);
      opacity: 0.45;
      transition: width 0.4s, height 0.4s, opacity 0.4s;
      will-change: transform;
    }
    body:has(a:hover) #cursor-ring,
    body:has(button:hover) #cursor-ring {
      width: 54px; height: 54px; opacity: 0.7;
    }

    /* ══════════════════════════════════════════════════
       4. NEURAL-NETWORK CANVAS BACKGROUND
    ══════════════════════════════════════════════════ */
    #neural-canvas {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      z-index: 0;
      pointer-events: none;
      opacity: 0.35;
    }

    /* ══════════════════════════════════════════════════
       5. NAVIGATION
    ══════════════════════════════════════════════════ */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      z-index: 1000;
      background: var(--nav-bg);
      backdrop-filter: blur(20px) saturate(1.5);
      -webkit-backdrop-filter: blur(20px) saturate(1.5);
      border-bottom: 1px solid var(--border);
      padding: 0 5vw;
      display: flex; align-items: center; justify-content: space-between;
      height: 64px;
      transition: background var(--transition);
    }
    .nav-logo {
      font-family: var(--font-head);
      font-size: 1.25rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, var(--accent-1), var(--accent-2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .nav-links {
      display: flex; gap: 2rem; align-items: center;
    }
    .nav-links a {
      font-size: 0.85rem;
      font-weight: 500;
      color: var(--text-sub);
      letter-spacing: 0.04em;
      text-transform: uppercase;
      position: relative;
      transition: color var(--transition);
    }
    .nav-links a::after {
      content: '';
      position: absolute; bottom: -3px; left: 0;
      width: 0; height: 2px;
      background: var(--accent-1);
      transition: width var(--transition);
      border-radius: 2px;
    }
    .nav-links a:hover { color: var(--text-main); }
    .nav-links a:hover::after { width: 100%; }

    /* Theme toggle */
    #theme-toggle {
      width: 42px; height: 42px;
      border-radius: 50%;
      border: 1px solid var(--border);
      background: var(--bg-card);
      color: var(--text-main);
      font-size: 1rem;
      display: flex; align-items: center; justify-content: center;
      transition: background var(--transition), transform 0.3s;
    }
    #theme-toggle:hover { transform: rotate(20deg) scale(1.1); }

    /* Hamburger (mobile) */
    #hamburger {
      display: none; flex-direction: column; gap: 5px;
      background: none; border: none;
      padding: 6px;
    }
    #hamburger span {
      display: block; width: 24px; height: 2px;
      background: var(--text-main);
      border-radius: 2px;
      transition: var(--transition);
    }
    .mobile-menu {
      display: none;
      position: fixed; top: 64px; left: 0; right: 0;
      background: var(--nav-bg);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border-bottom: 1px solid var(--border);
      flex-direction: column; gap: 0;
      z-index: 999;
    }
    .mobile-menu.open { display: flex; }
    .mobile-menu a {
      padding: 1rem 5vw;
      font-size: 0.95rem;
      font-weight: 500;
      color: var(--text-sub);
      border-bottom: 1px solid var(--border);
      transition: color var(--transition), padding-left var(--transition);
    }
    .mobile-menu a:hover { color: var(--accent-1); padding-left: calc(5vw + 8px); }

    /* ══════════════════════════════════════════════════
       6. LAYOUT HELPERS
    ══════════════════════════════════════════════════ */
    .container {
      position: relative; z-index: 1;
      max-width: 1160px;
      margin: 0 auto;
      padding: 0 5vw;
    }
    section { padding: 100px 0; }
    .section-label {
      display: inline-block;
      font-size: 0.75rem;
      font-weight: 600;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent-1);
      margin-bottom: 0.6rem;
    }
    .section-title {
      font-family: var(--font-head);
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 800;
      line-height: 1.1;
      letter-spacing: -0.03em;
      margin-bottom: 0.5rem;
    }
    .section-sub {
      color: var(--text-sub);
      font-size: 1.05rem;
      max-width: 560px;
      margin-bottom: 3.5rem;
    }
    .divider {
      width: 48px; height: 3px;
      background: linear-gradient(90deg, var(--accent-1), var(--accent-2));
      border-radius: 3px;
      margin: 1rem 0 2.5rem;
    }

    /* Reveal animation */
    .reveal {
      opacity: 0;
      transform: translateY(40px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ══════════════════════════════════════════════════
       7. HERO SECTION
    ══════════════════════════════════════════════════ */
    #hero {
      min-height: 100vh;
      display: flex; align-items: center;
      padding-top: 64px;
      position: relative; overflow: hidden;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 420px;
      gap: 4rem;
      align-items: center;
      width: 100%;
    }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: var(--tag-bg);
      color: var(--tag-color);
      border: 1px solid rgba(0,245,196,0.18);
      padding: 6px 16px;
      border-radius: 100px;
      font-size: 0.78rem;
      font-weight: 600;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      margin-bottom: 1.4rem;
      animation: fadeSlideDown 0.8s ease both;
    }
    .hero-badge i { font-size: 0.7rem; }
    .hero-name {
      font-family: var(--font-head);
      font-size: clamp(2.8rem, 6vw, 5rem);
      font-weight: 800;
      line-height: 1.0;
      letter-spacing: -0.04em;
      margin-bottom: 0.8rem;
      animation: fadeSlideDown 0.9s ease both 0.1s;
    }
    .hero-name span {
      background: linear-gradient(135deg, var(--accent-1) 0%, var(--accent-2) 50%, var(--accent-3) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .hero-title {
      font-size: 1.2rem;
      font-weight: 500;
      color: var(--text-sub);
      margin-bottom: 1.4rem;
      animation: fadeSlideDown 1.0s ease both 0.2s;
    }
    .hero-title b { color: var(--accent-1); font-weight: 600; }
    .hero-desc {
      color: var(--text-sub);
      font-size: 1.0rem;
      max-width: 500px;
      line-height: 1.75;
      margin-bottom: 2.4rem;
      animation: fadeSlideDown 1.1s ease both 0.3s;
    }
    .hero-cta {
      display: flex; gap: 1rem; flex-wrap: wrap;
      animation: fadeSlideDown 1.2s ease both 0.4s;
    }
    .btn {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 13px 28px;
      border-radius: 100px;
      font-weight: 600;
      font-size: 0.9rem;
      transition: transform 0.25s, box-shadow 0.25s, background 0.25s;
      position: relative; overflow: hidden;
    }
    .btn::before {
      content: '';
      position: absolute; inset: 0;
      background: rgba(255,255,255,0.08);
      opacity: 0;
      transition: opacity 0.25s;
    }
    .btn:hover::before { opacity: 1; }
    .btn:hover { transform: translateY(-3px); box-shadow: 0 12px 30px rgba(0,0,0,0.25); }
    .btn-primary {
      background: linear-gradient(135deg, var(--accent-1), var(--accent-2));
      color: #0a0a12;
      font-weight: 700;
    }
    .btn-outline {
      border: 1.5px solid var(--border);
      background: transparent;
      color: var(--text-main);
    }
    .btn-outline:hover { border-color: var(--accent-1); color: var(--accent-1); }

    /* Hero profile card */
    .hero-card {
      position: relative;
      animation: fadeSlideLeft 1.1s ease both 0.2s;
    }
    .hero-photo-wrap {
      position: relative;
      border-radius: var(--radius-lg);
      overflow: hidden;
      aspect-ratio: 4/5;
      background: linear-gradient(135deg, var(--bg-card), var(--accent-2));
      border: 1px solid var(--border);
      box-shadow: var(--shadow-card);
    }
    .hero-photo-wrap img {
      width: 100%; height: 100%;
      object-fit: cover;
      transition: transform 0.5s ease;
    }
    .hero-photo-wrap:hover img { transform: scale(1.04); }

    /* Floating stats */
    .float-stat {
      position: absolute;
      background: var(--bg-glass);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 12px 18px;
      display: flex; align-items: center; gap: 10px;
      box-shadow: 0 8px 24px rgba(0,0,0,0.2);
      white-space: nowrap;
    }
    .float-stat .stat-icon {
      width: 36px; height: 36px;
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1rem;
    }
    .float-stat .stat-num {
      font-family: var(--font-head);
      font-size: 1.1rem;
      font-weight: 800;
      line-height: 1;
    }
    .float-stat .stat-lbl {
      font-size: 0.72rem;
      color: var(--text-sub);
      line-height: 1.2;
    }
    .fs-1 { bottom: -18px; left: -28px; animation: float1 4s ease-in-out infinite; }
    .fs-2 { top: 24px; right: -28px; animation: float2 5s ease-in-out infinite; }
    .fs-3 { bottom: 90px; right: -24px; animation: float1 4.5s ease-in-out infinite 1s; }

    /* Hero social strip */
    .hero-social {
      display: flex; gap: 0.8rem; flex-wrap: wrap;
      margin-top: 2rem;
      animation: fadeSlideDown 1.3s ease both 0.5s;
    }
    .social-pill {
      display: inline-flex; align-items: center; gap: 6px;
      padding: 7px 14px;
      border-radius: 100px;
      background: var(--bg-card);
      border: 1px solid var(--border);
      font-size: 0.8rem;
      font-weight: 500;
      color: var(--text-sub);
      transition: border-color var(--transition), color var(--transition), transform 0.25s;
    }
    .social-pill:hover {
      border-color: var(--accent-1);
      color: var(--accent-1);
      transform: translateY(-2px);
    }
    .social-pill i { font-size: 0.9rem; }

    /* ══════════════════════════════════════════════════
       8. ABOUT SECTION
    ══════════════════════════════════════════════════ */
    #about {
      background: var(--bg-panel);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
    }
    .about-img-wrap {
      position: relative;
      border-radius: var(--radius-lg);
      overflow: hidden;
      aspect-ratio: 1/1;
      background: linear-gradient(135deg, var(--accent-2), var(--accent-1));
    }
    .about-img-wrap img {
      width: 100%; height: 100%;
      object-fit: cover;
    }
    .about-tag-grid {
      display: flex; flex-wrap: wrap; gap: 8px;
      margin-top: 1.5rem;
    }
    .about-tag {
      padding: 5px 14px;
      border-radius: 100px;
      background: var(--tag-bg);
      color: var(--tag-color);
      font-size: 0.78rem;
      font-weight: 600;
      border: 1px solid rgba(0,245,196,0.15);
    }
    .about-info-row {
      display: flex; gap: 1rem; margin-top: 1.5rem;
    }
    .info-chip {
      display: flex; align-items: center; gap: 8px;
      padding: 10px 16px;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      font-size: 0.83rem;
      color: var(--text-sub);
      flex: 1;
    }
    .info-chip i { color: var(--accent-1); }

    /* ══════════════════════════════════════════════════
       9. SKILLS SECTION
    ══════════════════════════════════════════════════ */
    .skills-top-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 2rem;
      margin-bottom: 3rem;
    }
    .skill-category-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 1.8rem;
      transition: box-shadow var(--transition), transform var(--transition);
    }
    .skill-category-card:hover {
      transform: translateY(-4px);
      box-shadow: var(--shadow-card);
    }
    .skill-cat-title {
      font-family: var(--font-head);
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--accent-1);
      margin-bottom: 1.2rem;
    }
    .skill-bar-row {
      margin-bottom: 1rem;
    }
    .skill-bar-label {
      display: flex; justify-content: space-between;
      font-size: 0.85rem;
      font-weight: 500;
      margin-bottom: 6px;
      color: var(--text-main);
    }
    .skill-bar-label span { color: var(--text-muted); font-size: 0.78rem; }
    .skill-bar-track {
      height: 6px;
      background: var(--skill-bar);
      border-radius: 6px;
      overflow: hidden;
    }
    .skill-bar-fill {
      height: 100%;
      border-radius: 6px;
      background: linear-gradient(90deg, var(--accent-1), var(--accent-2));
      width: 0;
      transition: width 1.4s cubic-bezier(0.4,0,0.2,1);
    }

    /* Tools grid */
    .tools-grid {
      display: flex; flex-wrap: wrap; gap: 10px;
    }
    .tool-chip {
      display: inline-flex; align-items: center; gap: 7px;
      padding: 7px 14px;
      border-radius: var(--radius-sm);
      background: var(--bg-card);
      border: 1px solid var(--border);
      font-size: 0.8rem;
      font-weight: 500;
      color: var(--text-sub);
      transition: border-color var(--transition), color var(--transition), transform 0.25s;
    }
    .tool-chip:hover {
      border-color: var(--accent-1);
      color: var(--text-main);
      transform: translateY(-2px);
    }
    .tool-chip i { font-size: 1rem; }

    /* ══════════════════════════════════════════════════
       10. PROJECTS SECTION
    ══════════════════════════════════════════════════ */
    #projects { background: var(--bg-panel); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 2rem;
    }
    .project-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      overflow: hidden;
      display: flex; flex-direction: column;
      transition: transform var(--transition), box-shadow var(--transition);
      position: relative;
    }
    .project-card:hover {
      transform: translateY(-8px) rotateX(2deg);
      box-shadow: var(--shadow-card-hover);
    }
    .project-card::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(90deg, var(--accent-1), var(--accent-2), var(--accent-3));
    }

    /* 3‑D image wrapper */
    .proj-img-wrap {
      position: relative;
      aspect-ratio: 16/9;
      overflow: hidden;
      background: linear-gradient(135deg, #1a1a28, #0d0d18);
    }
    .proj-img-wrap img {
      width: 100%; height: 100%;
      object-fit: cover;
      transition: transform 0.6s ease;
    }
    .project-card:hover .proj-img-wrap img { transform: scale(1.08); }
    .proj-img-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(to top, rgba(9,9,15,0.8) 0%, transparent 60%);
      pointer-events: none;
    }
    .proj-badge {
      position: absolute; top: 14px; left: 14px;
      background: var(--accent-1);
      color: #06060e;
      font-size: 0.7rem;
      font-weight: 700;
      padding: 4px 12px;
      border-radius: 100px;
      letter-spacing: 0.05em;
      text-transform: uppercase;
    }
    .proj-links-float {
      position: absolute; top: 14px; right: 14px;
      display: flex; gap: 8px;
      opacity: 0;
      transform: translateY(-6px);
      transition: opacity 0.3s, transform 0.3s;
    }
    .project-card:hover .proj-links-float { opacity: 1; transform: translateY(0); }
    .proj-link-btn {
      width: 34px; height: 34px;
      border-radius: 50%;
      background: var(--bg-glass);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
      border: 1px solid rgba(255,255,255,0.15);
      color: #fff;
      display: flex; align-items: center; justify-content: center;
      font-size: 0.8rem;
      transition: background 0.2s;
    }
    .proj-link-btn:hover { background: var(--accent-1); color: #06060e; }

    .proj-body { padding: 1.8rem; flex: 1; display: flex; flex-direction: column; gap: 0.8rem; }
    .proj-title {
      font-family: var(--font-head);
      font-size: 1.15rem;
      font-weight: 700;
      line-height: 1.3;
    }
    .proj-desc { color: var(--text-sub); font-size: 0.88rem; line-height: 1.65; }
    .proj-metric {
      display: flex; gap: 1rem;
      margin-top: 0.5rem;
    }
    .metric-chip {
      display: flex; align-items: center; gap: 6px;
      font-size: 0.8rem;
      font-weight: 600;
      color: var(--accent-1);
    }
    .metric-chip i { font-size: 0.75rem; }
    .proj-tags {
      display: flex; flex-wrap: wrap; gap: 6px;
      margin-top: auto; padding-top: 1rem;
    }
    .proj-tag {
      padding: 4px 11px;
      border-radius: 4px;
      background: var(--tag-bg);
      color: var(--tag-color);
      font-size: 0.73rem;
      font-weight: 600;
    }
    .proj-footer {
      padding: 1rem 1.8rem;
      border-top: 1px solid var(--border);
      display: flex; gap: 1rem;
    }
    .proj-footer a {
      display: inline-flex; align-items: center; gap: 6px;
      font-size: 0.82rem;
      font-weight: 600;
      color: var(--text-sub);
      transition: color var(--transition);
    }
    .proj-footer a:hover { color: var(--accent-1); }
    .proj-footer a i { font-size: 0.78rem; }

    /* ══════════════════════════════════════════════════
       11. EDUCATION SECTION
    ══════════════════════════════════════════════════ */
    .edu-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      overflow: hidden;
    }
    .edu-uni-banner {
      position: relative;
      height: 180px;
      background: linear-gradient(135deg, #0d1b2a, #1b2a3b, #0f2044);
      overflow: hidden;
    }
    .edu-uni-banner img {
      width: 100%; height: 100%;
      object-fit: cover;
    }
    .edu-uni-banner-overlay {
      position: absolute; inset: 0;
      display: flex; align-items: center;
      padding: 2rem;
    }
    .edu-uni-label {
      font-family: var(--font-head);
      font-size: 1.5rem;
      font-weight: 800;
      color: #fff;
      text-shadow: 0 2px 12px rgba(0,0,0,0.5);
    }
    .edu-body {
      padding: 2.5rem;
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 2rem;
      align-items: start;
    }
    .edu-degree {
      font-family: var(--font-head);
      font-size: 1.5rem;
      font-weight: 800;
      margin-bottom: 0.4rem;
    }
    .edu-inst {
      color: var(--accent-1);
      font-weight: 600;
      font-size: 0.95rem;
      margin-bottom: 0.3rem;
    }
    .edu-dept { color: var(--text-sub); font-size: 0.85rem; margin-bottom: 1.2rem; }
    .edu-pills { display: flex; gap: 0.7rem; flex-wrap: wrap; }
    .edu-pill {
      display: flex; align-items: center; gap: 6px;
      padding: 6px 14px;
      border-radius: 100px;
      background: var(--tag-bg);
      color: var(--tag-color);
      font-size: 0.78rem;
      font-weight: 600;
      border: 1px solid rgba(0,245,196,0.15);
    }
    .edu-cgpa {
      background: linear-gradient(135deg, var(--accent-1), var(--accent-2));
      border-radius: var(--radius-md);
      padding: 1.5rem 2rem;
      text-align: center;
      min-width: 130px;
    }
    .cgpa-num {
      font-family: var(--font-head);
      font-size: 2.2rem;
      font-weight: 800;
      color: #06060e;
      line-height: 1;
    }
    .cgpa-label {
      font-size: 0.72rem;
      font-weight: 700;
      color: rgba(0,0,0,0.6);
      text-transform: uppercase;
      letter-spacing: 0.1em;
      margin-top: 4px;
    }

    /* ══════════════════════════════════════════════════
       12. PUBLICATIONS SECTION
    ══════════════════════════════════════════════════ */
    #publications { background: var(--bg-panel); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
    .pub-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-lg);
      overflow: hidden;
      display: flex;
      gap: 0;
      transition: box-shadow var(--transition), transform var(--transition);
    }
    .pub-card:hover { transform: translateY(-4px); box-shadow: var(--shadow-card); }
    .pub-img-col {
      width: 280px; flex-shrink: 0;
      background: var(--bg-panel);
      position: relative; overflow: hidden;
      display: flex; align-items: center; justify-content: center;
      border-right: 1px solid var(--border);
    }
    .pub-img-col img {
      width: 100%; height: 100%;
      object-fit: contain;
      padding: 1.5rem;
      transition: transform 0.5s ease;
    }
    .pub-card:hover .pub-img-col img { 
      transform: scale(1.06); 
    }
    .pub-img-col::after {
      display: none;
    }
    .pub-body { padding: 2.5rem; flex: 1; }
    .pub-status {
      display: inline-flex; align-items: center; gap: 7px;
      padding: 5px 14px;
      border-radius: 100px;
      background: rgba(255,209,102,0.12);
      color: var(--accent-4);
      font-size: 0.75rem;
      font-weight: 700;
      border: 1px solid rgba(255,209,102,0.2);
      margin-bottom: 1rem;
      letter-spacing: 0.05em;
      text-transform: uppercase;
    }
    .pub-status i { animation: pulse 2s infinite; }
    .pub-title {
      font-family: var(--font-head);
      font-size: 1.2rem;
      font-weight: 700;
      line-height: 1.4;
      margin-bottom: 1rem;
    }
    .pub-meta {
      display: flex; flex-wrap: wrap; gap: 1rem;
      color: var(--text-sub);
      font-size: 0.83rem;
    }
    .pub-meta span { display: flex; align-items: center; gap: 5px; }
    .pub-meta i { color: var(--accent-1); }
    .pub-tags { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 1.2rem; }

    /* ══════════════════════════════════════════════════
       13. CERTIFICATIONS SECTION
    ══════════════════════════════════════════════════ */
    .certs-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.5rem;
    }
    .cert-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      overflow: hidden;
      position: relative;
      transition: transform var(--transition), box-shadow var(--transition);
    }
    .cert-card:hover { transform: translateY(-5px); box-shadow: var(--shadow-card); }
    .cert-img-wrap {
      position: relative;
      aspect-ratio: 16/9;
      background: linear-gradient(135deg, #0f1020, #1a1a30);
      overflow: hidden;
    }
    .cert-img-wrap img {
      width: 100%; height: 100%;
      object-fit: cover;
      transition: transform 0.5s ease;
    }
    .cert-card:hover .cert-img-wrap img { transform: scale(1.06); }
    .cert-img-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(to top, rgba(9,9,15,0.7) 0%, transparent 50%);
    }
    .cert-platform-badge {
      position: absolute; top: 10px; left: 10px;
      display: flex; align-items: center; gap: 6px;
      background: var(--bg-glass);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: 6px;
      padding: 4px 10px;
      font-size: 0.7rem;
      font-weight: 700;
      color: #fff;
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }
    .cert-body { padding: 1.2rem; }
    .cert-name {
      font-size: 0.9rem;
      font-weight: 600;
      line-height: 1.4;
      margin-bottom: 0.6rem;
    }
    .cert-link {
      display: inline-flex; align-items: center; gap: 5px;
      font-size: 0.77rem;
      font-weight: 600;
      color: var(--accent-1);
      transition: gap 0.2s;
    }
    .cert-link:hover { gap: 8px; }
    .cert-link i { font-size: 0.7rem; }

    /* ══════════════════════════════════════════════════
       14. RESEARCH INTERESTS
    ══════════════════════════════════════════════════ */
    .interests-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1.2rem;
    }
    .interest-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 1.6rem;
      text-align: center;
      transition: transform var(--transition), border-color var(--transition);
      position: relative; overflow: hidden;
    }
    .interest-card::before {
      content: '';
      position: absolute; inset: 0;
      background: radial-gradient(ellipse at center, var(--accent-1) 0%, transparent 70%);
      opacity: 0;
      transition: opacity 0.4s;
    }
    .interest-card:hover::before { opacity: 0.05; }
    .interest-card:hover { transform: translateY(-4px); border-color: rgba(0,245,196,0.25); }
    .interest-icon {
      width: 52px; height: 52px;
      border-radius: var(--radius-sm);
      background: var(--tag-bg);
      display: flex; align-items: center; justify-content: center;
      margin: 0 auto 1rem;
      font-size: 1.4rem;
      color: var(--accent-1);
    }
    .interest-name {
      font-family: var(--font-head);
      font-size: 0.88rem;
      font-weight: 700;
      color: var(--text-main);
    }

    /* ══════════════════════════════════════════════════
       15. EXTRA ACTIVITIES
    ══════════════════════════════════════════════════ */
    #activities { background: var(--bg-panel); border-top: 1px solid var(--border); }
    .activities-list { display: flex; flex-direction: column; gap: 1.2rem; }
    .activity-card {
      display: flex; gap: 1.4rem; align-items: start;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 1.6rem;
      transition: transform var(--transition), box-shadow var(--transition);
    }
    .activity-card:hover { transform: translateX(6px); box-shadow: var(--shadow-card); }
    .act-icon {
      width: 46px; height: 46px; flex-shrink: 0;
      border-radius: 10px;
      background: var(--tag-bg);
      display: flex; align-items: center; justify-content: center;
      font-size: 1.3rem;
      color: var(--accent-1);
    }
    .act-title { font-weight: 700; margin-bottom: 0.3rem; }
    .act-desc { font-size: 0.85rem; color: var(--text-sub); line-height: 1.55; }
    .act-cert-link {
      display: inline-flex; align-items: center; gap: 5px;
      font-size: 0.78rem;
      font-weight: 600;
      color: var(--accent-1);
      margin-top: 0.6rem;
      transition: gap 0.2s;
    }
    .act-cert-link:hover { gap: 8px; }

    /* ══════════════════════════════════════════════════
       16. CONTACT SECTION
    ══════════════════════════════════════════════════ */
    #contact { border-top: 1px solid var(--border); }
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }
    .contact-info-list { display: flex; flex-direction: column; gap: 1rem; margin-top: 1.5rem; }
    .contact-item {
      display: flex; align-items: center; gap: 1rem;
      padding: 1.2rem 1.4rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      transition: border-color var(--transition), transform 0.25s;
    }
    .contact-item:hover { border-color: var(--accent-1); transform: translateX(4px); }
    .contact-icon {
      width: 42px; height: 42px; flex-shrink: 0;
      border-radius: 10px;
      background: var(--tag-bg);
      display: flex; align-items: center; justify-content: center;
      font-size: 1rem;
      color: var(--accent-1);
    }
    .contact-label { font-size: 0.73rem; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.07em; }
    .contact-val { font-weight: 600; font-size: 0.9rem; }
    .contact-val a { color: var(--text-main); transition: color var(--transition); }
    .contact-val a:hover { color: var(--accent-1); }

    /* Social wall */
    .social-wall {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
      margin-top: 1.5rem;
    }
    .social-card {
      display: flex; align-items: center; gap: 12px;
      padding: 1rem 1.2rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      transition: transform 0.25s, border-color var(--transition);
    }
    .social-card:hover { transform: translateY(-3px); }
    .social-card.gh { --sc:#24292e; } .social-card.gh:hover { border-color: #6e40c9; }
    .social-card.li { --sc:#0077b5; } .social-card.li:hover { border-color: #0077b5; }
    .social-card.kgl { --sc:#20beff; } .social-card.kgl:hover { border-color: #20beff; }
    .social-card.web { --sc:#00f5c4; } .social-card.web:hover { border-color: var(--accent-1); }
    .social-card.wa { --sc:#25d366; } .social-card.wa:hover { border-color: #25d366; }
    .social-card.em { --sc:#ff6b6b; } .social-card.em:hover { border-color: #ff6b6b; }
    .sc-icon {
      width: 38px; height: 38px; border-radius: 9px;
      background: color-mix(in srgb, var(--sc) 18%, transparent);
      display: flex; align-items: center; justify-content: center;
      font-size: 1.1rem;
      color: var(--sc);
      flex-shrink: 0;
    }
    .sc-name { font-size: 0.78rem; font-weight: 700; }
    .sc-handle { font-size: 0.7rem; color: var(--text-muted); }

    /* ══════════════════════════════════════════════════
       17. FOOTER
    ══════════════════════════════════════════════════ */
    footer {
      position: relative; z-index: 1;
      background: var(--bg-panel);
      border-top: 1px solid var(--border);
      padding: 3rem 5vw;
      text-align: center;
    }
    .footer-name {
      font-family: var(--font-head);
      font-size: 1.6rem;
      font-weight: 800;
      background: linear-gradient(135deg, var(--accent-1), var(--accent-2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 0.4rem;
    }
    footer p { color: var(--text-muted); font-size: 0.82rem; margin-top: 0.5rem; }

    /* ══════════════════════════════════════════════════
       18. KEYFRAME ANIMATIONS
    ══════════════════════════════════════════════════ */
    @keyframes fadeSlideDown {
      from { opacity: 0; transform: translateY(-24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeSlideLeft {
      from { opacity: 0; transform: translateX(40px); }
      to   { opacity: 1; transform: translateX(0); }
    }
    @keyframes float1 {
      0%,100% { transform: translateY(0) rotate(0deg); }
      50%     { transform: translateY(-10px) rotate(2deg); }
    }
    @keyframes float2 {
      0%,100% { transform: translateY(0) rotate(0deg); }
      50%     { transform: translateY(8px) rotate(-2deg); }
    }
    @keyframes pulse {
      0%,100% { opacity: 1; }
      50%     { opacity: 0.4; }
    }
    @keyframes shimmer {
      0%   { background-position: -200% 0; }
      100% { background-position: 200% 0; }
    }

    /* ══════════════════════════════════════════════════
       19. SCROLL-TO-TOP BUTTON
    ══════════════════════════════════════════════════ */
    #scroll-top {
      position: fixed; bottom: 28px; right: 28px; z-index: 999;
      width: 46px; height: 46px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent-1), var(--accent-2));
      color: #06060e;
      border: none;
      font-size: 1rem;
      display: flex; align-items: center; justify-content: center;
      box-shadow: 0 8px 24px rgba(0,245,196,0.3);
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.3s, transform 0.3s;
      pointer-events: none;
    }
    #scroll-top.show { opacity: 1; transform: translateY(0); pointer-events: auto; }
    #scroll-top:hover { transform: translateY(-3px); box-shadow: 0 12px 30px rgba(0,245,196,0.45); }

    /* ══════════════════════════════════════════════════
       20. RESPONSIVE BREAKPOINTS
    ══════════════════════════════════════════════════ */
    @media (max-width: 1024px) {
      .hero-grid { grid-template-columns: 1fr; }
      .hero-card { max-width: 400px; margin: 0 auto; }
      .about-grid { grid-template-columns: 1fr; }
      .projects-grid { grid-template-columns: 1fr; }
      .pub-card { flex-direction: column; }
      .pub-img-col { width: 100%; height: 200px; }
      .pub-img-col::after { background: linear-gradient(to bottom, transparent, var(--bg-card)); }
      .contact-grid { grid-template-columns: 1fr; }
      .skills-top-grid { grid-template-columns: 1fr; }
    }
    @media (max-width: 768px) {
      section { padding: 70px 0; }
      .nav-links { display: none; }
      #hamburger { display: flex; }
      .edu-body { grid-template-columns: 1fr; }
      .social-wall { grid-template-columns: 1fr; }
      .hero-name { font-size: 2.4rem; }
      .float-stat.fs-1 { left: -10px; }
      .float-stat.fs-2 { right: -10px; }
      .float-stat.fs-3 { display: none; }
    }
    @media (max-width: 480px) {
      .hero-cta { flex-direction: column; }
      .btn { width: 100%; justify-content: center; }
      .certs-grid { grid-template-columns: 1fr; }
      .interests-grid { grid-template-columns: repeat(2,1fr); }
    }

    /* ══════════════════════════════════════════════════
       21. SECTION ACCENT BANDS
    ══════════════════════════════════════════════════ */
    .band {
      height: 1px;
      background: linear-gradient(90deg,
        transparent 0%,
        var(--accent-1) 30%,
        var(--accent-2) 70%,
        transparent 100%
      );
      opacity: 0.4;
    }
  </style>
</head>

<body>

  <!-- ══════════════════════════════════════════════════
       CUSTOM CURSOR
  ══════════════════════════════════════════════════ -->
  <div id="cursor-dot"></div>
  <div id="cursor-ring"></div>

  <!-- ══════════════════════════════════════════════════
       NEURAL NETWORK CANVAS BACKGROUND
  ══════════════════════════════════════════════════ -->
  <canvas id="neural-canvas"></canvas>

  <!-- ══════════════════════════════════════════════════
       NAVIGATION
  ══════════════════════════════════════════════════ -->
  <nav>
    <div class="nav-logo">Miraj</div>

    <!-- Desktop links -->
    <div class="nav-links">
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#education">Education</a>
      <a href="#publications">Research</a>
      <a href="#certifications">Certs</a>
      <a href="#contact">Contact</a>
    </div>

    <div style="display:flex;align-items:center;gap:0.8rem;">
      <button id="theme-toggle" aria-label="Toggle theme">
        <i class="fa-solid fa-sun" id="theme-icon"></i>
      </button>
      <button id="hamburger" aria-label="Menu">
        <span></span><span></span><span></span>
      </button>
    </div>
  </nav>

  <!-- Mobile navigation -->
  <div class="mobile-menu" id="mobile-menu">
    <a href="#about"         onclick="closeMobile()">About</a>
    <a href="#skills"        onclick="closeMobile()">Skills</a>
    <a href="#projects"      onclick="closeMobile()">Projects</a>
    <a href="#education"     onclick="closeMobile()">Education</a>
    <a href="#publications"  onclick="closeMobile()">Research</a>
    <a href="#certifications"onclick="closeMobile()">Certifications</a>
    <a href="#activities"    onclick="closeMobile()">Activities</a>
    <a href="#contact"       onclick="closeMobile()">Contact</a>
  </div>

  <!-- ══════════════════════════════════════════════════
       HERO
  ══════════════════════════════════════════════════ -->
  <section id="hero">
    <div class="container">
      <div class="hero-grid">

        <!-- Left: text -->
        <div>
          <div class="hero-badge">
            <i class="fa-solid fa-circle-dot"></i>
            Available for Research Collaboration
          </div>

          <h1 class="hero-name">
            Miraj<br><span>Ud Din</span>
          </h1>

          <p class="hero-title">
            <b>Artificial Intelligence Engineer</b> &amp; Researcher
          </p>

          <p class="hero-desc">
            Undergraduate AI student (CGPA 3.65/4.0) at the University of Agriculture Peshawar,
            specialising in Machine Learning, Deep Learning, and Data Science.
            Published ML researcher with deployed real-world applications.
          </p>

          <div class="hero-cta">
            <a href="downloads/Miraj_Ud_Din_CV.pdf" target="_blank" class="btn btn-primary">
              <i class="fa-solid fa-file-pdf"></i> Download CV
            </a>
            <a href="#projects" class="btn btn-primary">
              <i class="fa-solid fa-rocket"></i> View Projects
            </a>
          </div>

          <!-- Social pills -->
          <div class="hero-social">
            <a href="https://github.com/mirajuddin1357" target="_blank" class="social-pill">
              <i class="fa-brands fa-github"></i> GitHub
            </a>
            <a href="https://linkedin.com/in/mirajuddin1357" target="_blank" class="social-pill">
              <i class="fa-brands fa-linkedin"></i> LinkedIn
            </a>
            <a href="https://www.kaggle.com/mirajuddin1357" target="_blank" class="social-pill">
              <i class="fa-brands fa-kaggle"></i> Kaggle
            </a>
            <a href="https://wa.me/923060213131" target="_blank" class="social-pill">
              <i class="fa-brands fa-whatsapp"></i> WhatsApp
            </a>
          </div>
        </div>

        <!-- Right: photo card -->
        <div class="hero-card">
          <div class="hero-photo-wrap">
            <!--
              ╔═══════════════════════════════════════════════╗
              ║  REPLACE this src with your profile photo URL ║
              ║  Recommended size: 480 × 600 px               ║
              ╚═══════════════════════════════════════════════╝
            -->
              <img src="images/profile.png" alt="Miraj Ud Din – AI Engineer" />
          </div>

          <!-- Floating stats -->
          <div class="float-stat fs-1">
            <div class="stat-icon" style="background:rgba(0,245,196,0.12);">
              <i class="fa-solid fa-brain" style="color:var(--accent-1);"></i>
            </div>
            <div>
              <div class="stat-num">18+</div>
              <div class="stat-lbl">ML Models<br>Evaluated</div>
            </div>
          </div>

          <div class="float-stat fs-2">
            <div class="stat-icon" style="background:rgba(123,94,167,0.15);">
              <i class="fa-solid fa-star" style="color:var(--accent-2);"></i>
            </div>
            <div>
              <div class="stat-num">3.65</div>
              <div class="stat-lbl">CGPA<br>/ 4.00</div>
            </div>
          </div>

          <div class="float-stat fs-3">
            <div class="stat-icon" style="background:rgba(255,107,107,0.12);">
              <i class="fa-solid fa-chart-line" style="color:var(--accent-3);"></i>
            </div>
            <div>
              <div class="stat-num">0.9013</div>
              <div class="stat-lbl">Best Model<br>R² Score</div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       ABOUT
  ══════════════════════════════════════════════════ -->
  <section id="about">
    <div class="container">
      <div class="about-grid">

        <!-- Text -->
        <div class="reveal" style="transition-delay:0.15s;">
          <span class="section-label">About Me</span>
          <h2 class="section-title">Building the Future<br>with Intelligence</h2>
          <div class="divider"></div>
          <p style="color:var(--text-sub);line-height:1.8;margin-bottom:1rem;">
            I am a 6th-semester Artificial Intelligence undergraduate at the
            <strong style="color:var(--text-main);">University of Agriculture, Peshawar</strong> (ICS/IT).
            My passion sits at the intersection of research and real-world deployment —
            turning raw datasets into intelligent, production-ready systems.
          </p>
          <p style="color:var(--text-sub);line-height:1.8;margin-bottom:1.5rem;">
            From building an 18-model comparative regression study with Optuna-optimised
            hyperparameters, to deploying live Streamlit applications, I strive to bridge
            the gap between academic research and practical AI solutions. I am currently
            pursuing opportunities in master's-level research.
          </p>

          <!-- Research tags -->
          <div class="about-tag-grid">
            <span class="about-tag">Machine Learning</span>
            <span class="about-tag">Deep Learning</span>
            <span class="about-tag">Data Science</span>
            <span class="about-tag">NLP</span>
            <span class="about-tag">Optimization</span>
            <span class="about-tag">AI Research</span>
          </div>

          <!-- Quick info chips -->
          <div class="about-info-row" style="flex-wrap:wrap;">
            <div class="info-chip">
              <i class="fa-solid fa-location-dot"></i> Peshawar, Pakistan
            </div>
            <div class="info-chip">
              <i class="fa-solid fa-language"></i> English · Urdu · Pashto
            </div>
            <div class="info-chip">
              <i class="fa-solid fa-graduation-cap"></i> BS AI – 2027
            </div>
          </div>
        </div>

        <!-- Image -->
        <div class="reveal">
          <div class="about-img-wrap">
            <!--
              ╔═════════════════════════════════════════════════╗
              ║  REPLACE this src with your about/casual photo  ║
              ║  Recommended: square image, 600 × 600 px        ║
              ╚═════════════════════════════════════════════════╝
            -->
              <img src="images/profile.svg" alt="Miraj Ud Din – AI Engineer" />
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       SKILLS
  ══════════════════════════════════════════════════ -->
  <section id="skills">
    <div class="container">
      <span class="section-label reveal">Technical Arsenal</span>
      <h2 class="section-title reveal">Skills &amp; Expertise</h2>
      <div class="divider reveal"></div>
      <p class="section-sub reveal">
        A full-stack AI toolkit — from raw data wrangling to hyperparameter tuning and web deployment.
      </p>

      <!-- Skill bars grid -->
      <div class="skills-top-grid">

        <!-- Programming -->
        <div class="skill-category-card reveal">
          <div class="skill-cat-title"><i class="fa-solid fa-code"></i> &nbsp;Programming Languages</div>

          <div class="skill-bar-row">
            <div class="skill-bar-label">Python (Libraries) <span>95%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="95"></div></div>
          </div>
          <div class="skill-bar-row">
            <div class="skill-bar-label">SQL <span>90%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="90"></div></div>
          </div>
          <div class="skill-bar-row">
            <div class="skill-bar-label">HTML . CSS . JS <span>60%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="60"></div></div>
          </div>
          <div class="skill-bar-row">
            <div class="skill-bar-label">C++ <span>50%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="50"></div></div>
          </div>
        </div>

        <!-- ML/AI Frameworks -->
        <div class="skill-category-card reveal" style="transition-delay:0.1s;">
          <div class="skill-cat-title"><i class="fa-solid fa-robot"></i> &nbsp;ML . Data Science . AI Frameworks</div>

          <div class="skill-bar-row">
            <div class="skill-bar-label">NumPy . Pandas . Matplotlib . Seaborn . Plotly <span>95%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="95"></div></div>
          </div>

          <div class="skill-bar-row">
            <div class="skill-bar-label">Scikit-learn <span>92%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="92"></div></div>
          </div>

          <div class="skill-bar-row">
            <div class="skill-bar-label">TensorFlow . Keras <span>82%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="82"></div></div>
          </div>

          <div class="skill-bar-row">
            <div class="skill-bar-label">XGBoost . LightGBM . CatBoost <span>88%</span></div>
            <div class="skill-bar-track"><div class="skill-bar-fill" data-width="88"></div></div>
          </div>
        </div>

      </div>

      <!-- Tools / Platforms chips -->
      <div class="skill-category-card reveal" style="margin-bottom:0;">
        <div class="skill-cat-title"><i class="fa-solid fa-toolbox"></i> &nbsp;Tools &amp; Platforms</div>
        <div class="tools-grid">
          <!-- Data -->
          <span class="tool-chip"><i class="devicon-numpy-original colored"></i> NumPy</span>
          <span class="tool-chip"><i class="devicon-pandas-original colored"></i> Pandas</span>
          <span class="tool-chip"><i class="fa-solid fa-chart-bar" style="color:#11a8cd;"></i> Matplotlib</span>
          <span class="tool-chip"><i class="fa-solid fa-palette" style="color:#ff6b9d;"></i> Seaborn</span>
          <span class="tool-chip"><i class="fa-solid fa-chart-pie" style="color:#636efa;"></i> Plotly</span>
          <!-- ML -->
          <span class="tool-chip"><i class="fa-solid fa-bolt" style="color:#f7b500;"></i> XGBoost</span>
          <span class="tool-chip"><i class="fa-solid fa-leaf" style="color:#4caf50;"></i> LightGBM</span>
          <span class="tool-chip"><i class="fa-solid fa-cat" style="color:#ff9d5c;"></i> CatBoost</span>
          <span class="tool-chip"><i class="devicon-tensorflow-original colored"></i> TensorFlow</span>
          <span class="tool-chip"><i class="fa-solid fa-network-wired" style="color:#d00000;"></i> Keras</span>
          <span class="tool-chip"><i class="fa-solid fa-brain" style="color:#00f5c4;"></i> ANN / CNN / RNN / LSTM</span>
          <span class="tool-chip"><i class="fa-solid fa-sliders" style="color:#7b5ea7;"></i> Optuna / TPE</span>
          <span class="tool-chip"><i class="fa-solid fa-scale-balanced" style="color:#ff6b6b;"></i> SMOTE</span>
          <!-- Dev tools -->
          <span class="tool-chip"><i class="devicon-git-plain colored"></i> Git &amp; GitHub</span>
          <span class="tool-chip"><i class="devicon-vscode-plain colored"></i> VS Code</span>
          <span class="tool-chip"><img src="https://antigravity.google/assets/image/antigravity-logo.png" alt="Antigravity" style="width: 16px; height: 16px;"> Antigravity</span>
          <span class="tool-chip"><i class="devicon-jupyter-plain colored"></i> Jupyter Notebook</span>
          <span class="tool-chip"><i class="fa-brands fa-google" style="color:#e9e8e3;"></i> Google Colab</span>
          <span class="tool-chip"><i class="fa-solid fa-stream" style="color:#ff4b4b;"></i> Streamlit</span>
          <span class="tool-chip"><i class="fa-solid fa-triangle" style="color:#000;"></i> Vercel</span>
          <span class="tool-chip"><i class="devicon-firebase-plain colored"></i> Firebase</span>
          <!-- Office -->
          <span class="tool-chip"><i class="fa-solid fa-file-excel" style="color:#217346;"></i> Excel</span>
          <span class="tool-chip"><i class="fa-solid fa-file-word" style="color:#2b579a;"></i> Word</span>
          <span class="tool-chip"><i class="fa-solid fa-file-powerpoint" style="color:#b7472a;"></i> PowerPoint</span>
          <span class="tool-chip"><i class="fa-solid fa-book" style="color:#a3c4f3;"></i> EndNote</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       PROJECTS
  ══════════════════════════════════════════════════ -->
  <section id="projects">
    <div class="container">
      <span class="section-label reveal">Work</span>
      <h2 class="section-title reveal">Projects</h2>
      <div class="divider reveal"></div>
      <p class="section-sub reveal">
        End-to-end machine learning systems — from raw data to live deployed applications.
      </p>

      <div class="projects-grid">

        <!-- ── Project 1: Smartphone Price ── -->
        <div class="project-card reveal">
          <div class="proj-img-wrap">
            <!--
              ╔════════════════════════════════════════════════════════════════════╗
              ║  REPLACE src with your Smartphone Price Prediction app screenshot  ║
              ╚════════════════════════════════════════════════════════════════════╝
            -->
            <img src="images/mobile_price_prediction.png" alt="Smartphone Price Prediction App" />
            <img
              src="https://placehold.co/700x394/0d1117/00f5c4?text=Smartphone+Price+Prediction+App"
              alt="Smartphone Price Prediction App"
            />
            <div class="proj-img-overlay"></div>
            <span class="proj-badge">Live ✓</span>

            <div class="proj-links-float">
              <a href="https://mobile-price-prediction-1.streamlit.app/" target="_blank"
                 class="proj-link-btn" title="Live App">
                <i class="fa-solid fa-arrow-up-right-from-square"></i>
              </a>
              <a href="https://github.com/mirajuddin1357/Mobile-Price-Prediction" target="_blank"
                 class="proj-link-btn" title="GitHub Repo">
                <i class="fa-brands fa-github"></i>
              </a>
            </div>
          </div>

          <div class="proj-body">
            <h3 class="proj-title">Smartphone Price Prediction<br><small style="font-weight:400;font-size:0.85rem;color:var(--text-sub);">Comparative ML Regression Analysis</small></h3>
            <p class="proj-desc">
              Built and evaluated <strong>18 regression algorithms</strong> on an uncleaned Kaggle smartphone dataset.
              Applied Optuna TPE over 50 trials for automated hyperparameter tuning.
              Deployed as a real-time Streamlit app with multi-currency output (PKR / USD / INR / CNY).
            </p>

            <div class="proj-metric">
              <div class="metric-chip"><i class="fa-solid fa-chart-line"></i> R² = 0.9013</div>
              <div class="metric-chip"><i class="fa-solid fa-bullseye"></i> MAE = 0.2102</div>
              <div class="metric-chip"><i class="fa-solid fa-flask"></i> 50 Optuna Trials</div>
            </div>

            <div class="proj-tags">
              <span class="proj-tag">XGBoost</span>
              <span class="proj-tag">Optuna</span>
              <span class="proj-tag">Streamlit</span>
              <span class="proj-tag">Python</span>
              <span class="proj-tag">Regression</span>
              <span class="proj-tag">18 Models</span>
            </div>
          </div>

          <div class="proj-footer">
            <a href="https://mobile-price-prediction-1.streamlit.app/" target="_blank">
              <i class="fa-solid fa-globe"></i> Live App
            </a>
            <a href="https://github.com/mirajuddin1357/Mobile-Price-Prediction" target="_blank">
              <i class="fa-brands fa-github"></i> GitHub Repo
            </a>
          </div>
        </div>

        <!-- ── Project 2: Credit Card Fraud ── -->
        <div class="project-card reveal" style="transition-delay:0.15s;">
          <div class="proj-img-wrap">
            <!--
              ╔══════════════════════════════════════════════════════════════════╗
              ║  REPLACE src with your Credit Card Fraud Detection app screenshot ║
              ╚══════════════════════════════════════════════════════════════════╝
            -->
            <img src="images/credit_card_fraud.png" alt="Credit Card Fraud Detection App" />
            <div class="proj-img-overlay"></div>
            <span class="proj-badge" style="background:var(--accent-3);">Live ✓</span>

            <div class="proj-links-float">
              <a href="https://credit-card-fraud-detection-classification.streamlit.app/" target="_blank"
                 class="proj-link-btn" title="Live App">
                <i class="fa-solid fa-arrow-up-right-from-square"></i>
              </a>
              <a href="https://github.com/mirajuddin1357/Credit-Card-Fraud-Detection" target="_blank"
                 class="proj-link-btn" title="GitHub Repo">
                <i class="fa-brands fa-github"></i>
              </a>
            </div>
          </div>

          <div class="proj-body">
            <h3 class="proj-title">Credit Card Fraud Detection<br><small style="font-weight:400;font-size:0.85rem;color:var(--text-sub);">ML Classification System</small></h3>
            <p class="proj-desc">
              Developed a classification pipeline detecting fraudulent transactions on a heavily
              imbalanced dataset(492 frauds out of 284,807 transactions). Applied <strong>SMOTE</strong> oversampling alongside Logistic Regression,
              Random Forest, and XGBoost. Evaluated with an accuracy of 99.9%, precision, recall, and F1-score.
              Deployed as a live Streamlit web app.
            </p>

            <div class="proj-metric">
              <div class="metric-chip"><i class="fa-solid fa-shield-halved"></i> Fraud Detection</div>
              <div class="metric-chip"><i class="fa-solid fa-scale-balanced"></i> SMOTE Applied</div>
              <div class="metric-chip"><i class="fa-solid fa-bolt"></i> XGBoost Winner</div>
            </div>

            <div class="proj-tags">
              <span class="proj-tag">Logistic Regression</span>
              <span class="proj-tag">Random Forest</span>
              <span class="proj-tag">XGBoost</span>
              <span class="proj-tag">SMOTE</span>
              <span class="proj-tag">Classification</span>
            </div>
          </div>

          <div class="proj-footer">
            <a href="https://credit-card-fraud-detection-classification.streamlit.app/" target="_blank">
              <i class="fa-solid fa-globe"></i> Live App
            </a>
            <a href="https://github.com/mirajuddin1357/Credit-Card-Fraud-Detection" target="_blank">
              <i class="fa-brands fa-github"></i> GitHub Repo
            </a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       EDUCATION
  ══════════════════════════════════════════════════ -->
  <section id="education">
    <div class="container">
      <span class="section-label reveal">Academic</span>
      <h2 class="section-title reveal">Education</h2>
      <div class="divider reveal"></div>

      <div class="edu-card reveal">

        <!-- University banner – replace with your uni image -->
        <div class="edu-uni-banner">
          <!--
            ╔════════════════════════════════════════════════════════════════════╗
            ║  REPLACE src with a wide (landscape) image of your university.     ║
            ║  Ideal size: ~1400 × 280 px  (wide banner)                         ║
            ╚════════════════════════════════════════════════════════════════════╝
          -->
          <img src="images/uap_campus_banner.png" alt="University of Agriculture, Peshawar" />
          <div class="edu-uni-banner-overlay">
            <span class="edu-uni-label">University of Agriculture, Peshawar</span>
          </div>
        </div>

        <div class="edu-body">
          <div>
            <h3 class="edu-degree">BS Artificial Intelligence</h3>
            <p class="edu-inst">University of Agriculture, Peshawar</p>
            <p class="edu-dept">Institute of Computer Sciences and Information Technology (ICS/IT)</p>
            <div class="edu-pills">
              <span class="edu-pill"><i class="fa-solid fa-calendar-days"></i> 2023 – 2027 (Expected)</span>
              <span class="edu-pill"><i class="fa-solid fa-layer-group"></i> 6th Semester</span>
              <span class="edu-pill"><i class="fa-solid fa-location-dot"></i> Peshawar, KPK</span>
            </div>
          </div>
          <div class="edu-cgpa">
            <div class="cgpa-num">3.65</div>
            <div class="cgpa-label">CGPA / 4.00</div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       PUBLICATIONS
  ══════════════════════════════════════════════════ -->
  <section id="publications">
    <div class="container">
      <span class="section-label reveal">Research</span>
      <h2 class="section-title reveal">Publications</h2>
      <div class="divider reveal"></div>

      <div class="pub-card reveal">

        <!-- Publication image -->
        <div class="pub-img-col">
          <!--
            Research / ML / journal illustration – freely replace.
          -->
          <img src="images/mobile_price_prediction_research_infographic.svg" alt="Machine Learning Research" />
        </div>

        <div class="pub-body">
          <div class="pub-status">
            <i class="fa-solid fa-circle"></i> Under Review — 2026
          </div>

          <h3 class="pub-title">
            A Comparative Analysis of Machine Learning Regression Models for Smartphone Price
            Prediction with Optuna Hyperparameter Optimisation and Streamlit Deployment
          </h3>

          <div class="pub-meta">
            <span><i class="fa-solid fa-user-pen"></i> Miraj Ud Din</span>
            <span><i class="fa-solid fa-calendar"></i> Journal Submission 2026</span>
            <span><i class="fa-solid fa-book-open"></i> Under Review</span>
          </div>

          <div class="pub-tags">
            <span class="proj-tag">Machine Learning</span>
            <span class="proj-tag">Regression</span>
            <span class="proj-tag">Optuna HPO</span>
            <span class="proj-tag">XGBoost</span>
            <span class="proj-tag">Streamlit</span>
            <span class="proj-tag">Smartphone Pricing</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       CERTIFICATIONS
  ══════════════════════════════════════════════════ -->
  <section id="certifications">
    <div class="container">
      <span class="section-label reveal">Credentials</span>
      <h2 class="section-title reveal">Certifications</h2>
      <div class="divider reveal"></div>
      <p class="section-sub reveal">
        Verified certifications from industry-leading platforms.
      </p>

      <div class="certs-grid">

        <!-- Helper macro: each cert card -->
        <!-- 1 – NAVTTC -->
        <div class="cert-card reveal">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/NAVTTC Certificate AI(ML, DL, C).png"
              alt="NAVTTC Certificate"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="fa-solid fa-award"></i> NAVTTC
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Artificial Intelligence (ML · DL · Communication)</p>
            <a href="images/certificates/NAVTTC Certificate AI(ML, DL, C).png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

        <!-- 2 – Azure AI-900 -->
        <div class="cert-card reveal" style="transition-delay:0.05s;">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/Microsoft Certified  Azure AI Fundamentals Credentials - mirajuddin-2209 _ Microsoft Learn.png"
              alt="Microsoft Azure AI-900"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="fa-brands fa-microsoft"></i> Microsoft Azure
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Azure AI Fundamentals — AI-900</p>
            <a href="images/certificates/Microsoft Certified  Azure AI Fundamentals Credentials - mirajuddin-2209 _ Microsoft Learn.png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

        <!-- 3 – DataCamp Data Science for Business -->
        <div class="cert-card reveal" style="transition-delay:0.1s;">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/datacamp-data-science-for-business-certificate.png"
              alt="DataCamp Data Science for Business"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="fa-solid fa-d"></i> DataCamp
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Data Science for Business</p>
            <a href="images/certificates/datacamp-data-science-for-business-certificate.png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

        <!-- 4 – Cisco Intro Data Science -->
        <div class="cert-card reveal" style="transition-delay:0.15s;">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/Cisco-Intro-to-Data-Science-Update20250925-31-lkdrnk.png"
              alt="Cisco Introduction to Data Science"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="fa-solid fa-network-wired"></i> Cisco
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Introduction to Data Science</p>
            <a href="images/certificates/Cisco-Intro-to-Data-Science-Update20250925-31-lkdrnk.png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

        <!-- 5 – DataCamp Python -->
        <div class="cert-card reveal" style="transition-delay:0.2s;">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/datacamp-introduction-to-python-certificate.png"
              alt="DataCamp Introduction to Python"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="devicon-python-plain"></i> DataCamp
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Introduction to Python</p>
            <a href="images/certificates/datacamp-introduction-to-python-certificate.png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

        <!-- 6 – DataCamp SQL -->
        <div class="cert-card reveal" style="transition-delay:0.25s;">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/datacamp-introduction-to-SQL-certificate.png"
              alt="DataCamp Introduction to SQL"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="fa-solid fa-database"></i> DataCamp
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Introduction to SQL</p>
            <a href="images/certificates/datacamp-introduction-to-SQL-certificate.png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

        <!-- 7 – DataCamp Excel -->
        <div class="cert-card reveal" style="transition-delay:0.3s;">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/datacamp-Introduction-to-excel-certificate.png"
              alt="DataCamp Introduction to Excel"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="fa-solid fa-file-excel"></i> DataCamp
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Introduction to Excel</p>
            <a href="images/certificates/datacamp-Introduction-to-excel-certificate.png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

        <!-- 8 – Typing.com -->
        <div class="cert-card reveal" style="transition-delay:0.35s;">
          <div class="cert-img-wrap">
            <img
              src="images/certificates/typing.com_certificate.png"
              alt="Typing.com Proficiency"
              loading="lazy"
            />
            <div class="cert-img-overlay"></div>
            <div class="cert-platform-badge">
              <i class="fa-solid fa-keyboard"></i> Typing.com
            </div>
          </div>
          <div class="cert-body">
            <p class="cert-name">Typing Proficiency</p>
            <a href="images/certificates/typing.com_certificate.png"
               target="_blank" class="cert-link">
              View Certificate <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       RESEARCH INTERESTS
  ══════════════════════════════════════════════════ -->
  <section id="research">
    <div class="container">
      <span class="section-label reveal">Focus Areas</span>
      <h2 class="section-title reveal">Research Interests</h2>
      <div class="divider reveal"></div>

      <div class="interests-grid">
        <div class="interest-card reveal">
          <div class="interest-icon"><i class="fa-solid fa-robot"></i></div>
          <div class="interest-name">Artificial Intelligence</div>
        </div>
        <div class="interest-card reveal" style="transition-delay:0.05s;">
          <div class="interest-icon"><i class="fa-solid fa-brain"></i></div>
          <div class="interest-name">Machine Learning</div>
        </div>
        <div class="interest-card reveal" style="transition-delay:0.1s;">
          <div class="interest-icon"><i class="fa-solid fa-network-wired"></i></div>
          <div class="interest-name">Deep Learning</div>
        </div>
        <div class="interest-card reveal" style="transition-delay:0.15s;">
          <div class="interest-icon"><i class="fa-solid fa-chart-line"></i></div>
          <div class="interest-name">Data Science</div>
        </div>
        <div class="interest-card reveal" style="transition-delay:0.2s;">
          <div class="interest-icon"><i class="fa-solid fa-magnifying-glass-chart"></i></div>
          <div class="interest-name">Data Analysis</div>
        </div>
        <div class="interest-card reveal" style="transition-delay:0.25s;">
          <div class="interest-icon"><i class="fa-solid fa-sliders"></i></div>
          <div class="interest-name">Optimization</div>
        </div>
        <div class="interest-card reveal" style="transition-delay:0.3s;">
          <div class="interest-icon"><i class="fa-solid fa-comment-dots"></i></div>
          <div class="interest-name">NLP</div>
        </div>
        <div class="interest-card reveal" style="transition-delay:0.35s;">
          <div class="interest-icon"><i class="fa-solid fa-flask"></i></div>
          <div class="interest-name">AI Research</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       EXTRA ACTIVITIES
  ══════════════════════════════════════════════════ -->
  <section id="activities">
    <div class="container">
      <span class="section-label reveal">Beyond Code</span>
      <h2 class="section-title reveal">Extra Activities</h2>
      <div class="divider reveal"></div>

      <div class="activities-list">

        <!-- LetTech Ramzan Series -->
        <div class="activity-card reveal">
          <div class="act-icon"><i class="fa-solid fa-lightbulb"></i></div>
          <div style="flex:1;">
            <div class="act-title">LetTech Ramzan Series 2026 — One-Week Bootcamp</div>
            <div class="act-desc">
              Intensive bootcamp covering: Entrepreneurship · AI Tools for Students ·
              AI in IT Operations · AI Cybersecurity &amp; SDGs · Career Crafting · Solutions That Save Lives.
            </div>
            <a href="images/certificates/Co-Curricular Activitie Certificate LetTech Ramazan Series 2026.png"
               target="_blank" class="act-cert-link">
              <i class="fa-solid fa-certificate"></i> View Certificate
              <i class="fa-solid fa-arrow-right"></i>
            </a>
          </div>
        </div>

        <!-- Career Direction Seminar -->
        <div class="activity-card reveal" style="transition-delay:0.1s;">
          <div class="act-icon"><i class="fa-solid fa-compass"></i></div>
          <div style="flex:1;">
            <div class="act-title">Career Direction Seminar</div>
            <div class="act-desc">
              Professional development seminar focused on career planning, academic pathways, and navigating the AI job market.
            </div>
            <a href="images/certificates/Co-Curricular Activitie Certificate participation-in-career-direction-uap.png"
               target="_blank" class="act-cert-link">
              <i class="fa-solid fa-certificate"></i> View Certificate
              <i class="fa-solid fa-arrow-right"></i>
            </a>
          </div>
        </div>

        <!-- Basic First Aid Training -->
        <div class="activity-card reveal" style="transition-delay:0.2s;">
          <div class="act-icon"><i class="fa-solid fa-briefcase-medical"></i></div>
          <div style="flex:1;">
            <div class="act-title">Basic First Aid Training — GHSS Barkhalozo</div>
            <div class="act-desc">
              Comprehensive training program covering essential first aid protocols, emergency response, and life-saving techniques.
            </div>
            <a href="images/certificates/Co-Curricular Activitie Certificate participation-in-basic-first-aid-training-in-GHSS-barkhalozo.png"
               target="_blank" class="act-cert-link">
              <i class="fa-solid fa-certificate"></i> View Certificate
              <i class="fa-solid fa-arrow-right"></i>
            </a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       CONTACT
  ══════════════════════════════════════════════════ -->
  <section id="contact">
    <div class="container">
      <span class="section-label reveal">Get In Touch</span>
      <h2 class="section-title reveal">Contact Me</h2>
      <div class="divider reveal"></div>

      <div class="contact-grid">

        <!-- Left: contact details -->
        <div class="reveal">
          <p style="color:var(--text-sub);line-height:1.8;margin-bottom:0.5rem;">
            Interested in research collaboration, scholarship inquiries,
            or just want to connect? I'd love to hear from you.
          </p>

          <div class="contact-info-list">

            <a href="mailto:mirajuddin1357@gmail.com" class="contact-item">
              <div class="contact-icon"><i class="fa-solid fa-envelope"></i></div>
              <div>
                <div class="contact-label">Email</div>
                <div class="contact-val">mirajuddin1357@gmail.com</div>
              </div>
            </a>

            <a href="https://maps.google.com/?q=Peshawar" target="_blank" class="contact-item">
              <div class="contact-icon"><i class="fa-solid fa-location-dot"></i></div>
              <div>
                <div class="contact-label">Location</div>
                <div class="contact-val">Peshawar, KPK, Pakistan</div>
              </div>
            </a>

          </div>
        </div>

        <!-- Right: social wall -->
        <div class="reveal" style="transition-delay:0.15s;">
          <p style="font-family:var(--font-head);font-weight:700;font-size:1.05rem;margin-bottom:0.5rem;">
            Connect on Socials
          </p>
          <div class="social-wall">

            <a href="https://github.com/mirajuddin1357" target="_blank" class="social-card gh">
              <div class="sc-icon"><i class="fa-brands fa-github"></i></div>
              <div>
                <div class="sc-name">GitHub</div>
                <div class="sc-handle">@mirajuddin1357</div>
              </div>
            </a>

            <a href="https://linkedin.com/in/mirajuddin1357" target="_blank" class="social-card li">
              <div class="sc-icon"><i class="fa-brands fa-linkedin"></i></div>
              <div>
                <div class="sc-name">LinkedIn</div>
                <div class="sc-handle">mirajuddin1357</div>
              </div>
            </a>

            <a href="https://www.kaggle.com/mirajuddin1357" target="_blank" class="social-card kgl">
              <div class="sc-icon"><i class="fa-brands fa-kaggle"></i></div>
              <div>
                <div class="sc-name">Kaggle</div>
                <div class="sc-handle">@mirajuddin1357</div>
              </div>
            </a>

            <a href="https://wa.me/923060213131" target="_blank" class="social-card wa">
              <div class="sc-icon"><i class="fa-brands fa-whatsapp"></i></div>
              <div>
                <div class="sc-name">WhatsApp</div>
                <div class="sc-handle">+92 306 021 3131</div>
              </div>
            </a>

            <a href="mailto:mirajuddin1357@gmail.com" class="social-card em">
              <div class="sc-icon"><i class="fa-solid fa-envelope"></i></div>
              <div>
                <div class="sc-name">Email</div>
                <div class="sc-handle">Gmail</div>
              </div>
            </a>

            <a href="downloads/Miraj_Ud_Din_CV.pdf" target="_blank" class="social-card web">
              <div class="sc-icon"><i class="fa-solid fa-file-pdf"></i></div>
              <div>
                <div class="sc-name">Download CV</div>
                <div class="sc-handle">Resume (PDF)</div>
              </div>
            </a>

          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══════════════════════════════════════════════════
       FOOTER
  ══════════════════════════════════════════════════ -->
  <footer>
    <div class="footer-name">Miraj Ud Din</div>
    <p>Artificial Intelligence Engineer &amp; Researcher · Peshawar, Pakistan</p>
    <p style="margin-top:1rem;">
      Built with HTML / CSS / JS ·
    </p>
    <p>© <span id="year"></span> Miraj Ud Din. All rights reserved.</p>
  </footer>

  <!-- Scroll-to-top -->
  <button id="scroll-top" aria-label="Scroll to top">
    <i class="fa-solid fa-arrow-up"></i>
  </button>

  <!-- ══════════════════════════════════════════════════
       JAVASCRIPT
  ══════════════════════════════════════════════════ -->
  <script>
  /* ────────────────────────────────────────────────────
     1. CURRENT YEAR
  ──────────────────────────────────────────────────── */
  document.getElementById('year').textContent = new Date().getFullYear();

  /* ────────────────────────────────────────────────────
     2. CUSTOM CURSOR
  ──────────────────────────────────────────────────── */
  const dot  = document.getElementById('cursor-dot');
  const ring = document.getElementById('cursor-ring');
  let mx = 0, my = 0, rx = 0, ry = 0;

  document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; });

  function animateCursor() {
    dot.style.left  = mx + 'px';
    dot.style.top   = my + 'px';
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx + 'px';
    ring.style.top  = ry + 'px';
    requestAnimationFrame(animateCursor);
  }
  animateCursor();

  /* ────────────────────────────────────────────────────
     3. NEURAL-NETWORK BACKGROUND CANVAS
  ──────────────────────────────────────────────────── */
  (function() {
    const canvas = document.getElementById('neural-canvas');
    const ctx    = canvas.getContext('2d');
    let W, H, nodes = [], animFrame;

    /* Node definition */
    function Node() {
      this.x  = Math.random() * W;
      this.y  = Math.random() * H;
      this.vx = (Math.random() - 0.5) * 0.4;
      this.vy = (Math.random() - 0.5) * 0.4;
      this.r  = Math.random() * 2.5 + 1;
      // Colour cycles through accent palette
      const hues = [174, 270, 0, 48];
      this.hue = hues[Math.floor(Math.random() * hues.length)];
    }
    Node.prototype.update = function() {
      this.x += this.vx;
      this.y += this.vy;
      if (this.x < 0 || this.x > W) this.vx *= -1;
      if (this.y < 0 || this.y > H) this.vy *= -1;
    };

    function init() {
      W = canvas.width  = window.innerWidth;
      H = canvas.height = window.innerHeight;
      const count = Math.min(Math.floor(W * H / 14000), 90);
      nodes = Array.from({ length: count }, () => new Node());
    }

    const CONNECT_DIST = 160;

    function draw() {
      ctx.clearRect(0, 0, W, H);

      /* Edges */
      for (let i = 0; i < nodes.length; i++) {
        for (let j = i + 1; j < nodes.length; j++) {
          const dx = nodes[i].x - nodes[j].x;
          const dy = nodes[i].y - nodes[j].y;
          const d  = Math.sqrt(dx * dx + dy * dy);
          if (d < CONNECT_DIST) {
            const alpha = (1 - d / CONNECT_DIST) * 0.55;
            ctx.beginPath();
            ctx.moveTo(nodes[i].x, nodes[i].y);
            ctx.lineTo(nodes[j].x, nodes[j].y);
            ctx.strokeStyle = `hsla(${nodes[i].hue},80%,65%,${alpha})`;
            ctx.lineWidth = 0.8;
            ctx.stroke();
          }
        }
      }

      /* Nodes */
      nodes.forEach(n => {
        ctx.beginPath();
        ctx.arc(n.x, n.y, n.r, 0, Math.PI * 2);
        ctx.fillStyle = `hsl(${n.hue},90%,70%)`;
        ctx.shadowColor = `hsl(${n.hue},90%,65%)`;
        ctx.shadowBlur = 8;
        ctx.fill();
        ctx.shadowBlur = 0;
        n.update();
      });

      animFrame = requestAnimationFrame(draw);
    }

    init();
    draw();
    window.addEventListener('resize', () => { init(); });
  })();

  /* ────────────────────────────────────────────────────
     4. DARK / LIGHT THEME TOGGLE
  ──────────────────────────────────────────────────── */
  const html      = document.documentElement;
  const themeBtn  = document.getElementById('theme-toggle');
  const themeIcon = document.getElementById('theme-icon');
  const saved     = localStorage.getItem('theme') || 'dark';
  html.setAttribute('data-theme', saved);
  themeIcon.className = saved === 'dark' ? 'fa-solid fa-sun' : 'fa-solid fa-moon';

  themeBtn.addEventListener('click', () => {
    const current = html.getAttribute('data-theme');
    const next    = current === 'dark' ? 'light' : 'dark';
    html.setAttribute('data-theme', next);
    localStorage.setItem('theme', next);
    themeIcon.className = next === 'dark' ? 'fa-solid fa-sun' : 'fa-solid fa-moon';
  });

  /* ────────────────────────────────────────────────────
     5. MOBILE HAMBURGER MENU
  ──────────────────────────────────────────────────── */
  const hamburger  = document.getElementById('hamburger');
  const mobileMenu = document.getElementById('mobile-menu');

  hamburger.addEventListener('click', () => {
    mobileMenu.classList.toggle('open');
  });

  function closeMobile() {
    mobileMenu.classList.remove('open');
  }

  /* ────────────────────────────────────────────────────
     6. SCROLL REVEAL (IntersectionObserver)
  ──────────────────────────────────────────────────── */
  const revealEls = document.querySelectorAll('.reveal');
  const revealObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          e.target.classList.add('visible');
          revealObserver.unobserve(e.target);
        }
      });
    },
    { threshold: 0.12 }
  );
  revealEls.forEach(el => revealObserver.observe(el));

  /* ────────────────────────────────────────────────────
     7. SKILL BAR ANIMATION
  ──────────────────────────────────────────────────── */
  const skillFills = document.querySelectorAll('.skill-bar-fill');
  const skillObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          const w = e.target.getAttribute('data-width');
          e.target.style.width = w + '%';
          skillObserver.unobserve(e.target);
        }
      });
    },
    { threshold: 0.3 }
  );
  skillFills.forEach(el => skillObserver.observe(el));

  /* ────────────────────────────────────────────────────
     8. SCROLL-TO-TOP BUTTON
  ──────────────────────────────────────────────────── */
  const scrollTopBtn = document.getElementById('scroll-top');
  window.addEventListener('scroll', () => {
    scrollTopBtn.classList.toggle('show', window.scrollY > 400);
  });
  scrollTopBtn.addEventListener('click', () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });

  /* ────────────────────────────────────────────────────
     9. ACTIVE NAV HIGHLIGHT on scroll
  ──────────────────────────────────────────────────── */
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');

  const navObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          navLinks.forEach(a => a.style.color = '');
          const active = document.querySelector(`.nav-links a[href="#${e.target.id}"]`);
          if (active) active.style.color = 'var(--accent-1)';
        }
      });
    },
    { threshold: 0.4 }
  );
  sections.forEach(s => navObserver.observe(s));

  /* ────────────────────────────────────────────────────
     10. 3‑D card tilt effect on project cards
  ──────────────────────────────────────────────────── */
  document.querySelectorAll('.project-card').forEach(card => {
    card.addEventListener('mousemove', e => {
      const rect = card.getBoundingClientRect();
      const x = ((e.clientX - rect.left) / rect.width  - 0.5) * 14;
      const y = ((e.clientY - rect.top)  / rect.height - 0.5) * -14;
      card.style.transform = `perspective(800px) rotateY(${x}deg) rotateX(${y}deg) translateY(-6px)`;
    });
    card.addEventListener('mouseleave', () => {
      card.style.transform = '';
    });
  });
  </script>

</body>
</html>
