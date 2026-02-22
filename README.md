<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pushwin T H — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Outfit:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg: #06080f;
  --s1: #0b0e1a;
  --s2: #0f1524;
  --s3: #141c2f;
  --border: rgba(255,255,255,0.06);
  --border2: rgba(0,200,255,0.15);
  --cyan: #00c8ff;
  --cyan-dim: rgba(0,200,255,0.12);
  --green: #00ff88;
  --green-dim: rgba(0,255,136,0.1);
  --amber: #ffb700;
  --rose: #ff4d6d;
  --text: #dde6f0;
  --muted: #4a5568;
  --muted2: #718096;
}

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Outfit', sans-serif;
  min-height: 100vh;
  overflow-x: hidden;
  cursor: none;
}

/* Custom cursor */
.cursor {
  position: fixed;
  width: 10px; height: 10px;
  background: var(--cyan);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  transform: translate(-50%, -50%);
  transition: transform 0.1s;
  box-shadow: 0 0 20px var(--cyan);
}
.cursor-ring {
  position: fixed;
  width: 32px; height: 32px;
  border: 1px solid rgba(0,200,255,0.4);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9998;
  transform: translate(-50%, -50%);
  transition: all 0.15s ease;
}

/* Starfield background */
.stars {
  position: fixed;
  inset: 0;
  z-index: 0;
  overflow: hidden;
  pointer-events: none;
}
.stars span {
  position: absolute;
  border-radius: 50%;
  background: white;
  animation: twinkle var(--d, 3s) var(--delay, 0s) infinite alternate;
  opacity: 0;
}
@keyframes twinkle {
  0% { opacity: 0; transform: scale(0.8); }
  100% { opacity: var(--op, 0.6); transform: scale(1); }
}

/* Glow orbs */
.orb {
  position: fixed;
  border-radius: 50%;
  filter: blur(120px);
  pointer-events: none;
  z-index: 0;
  animation: float 8s ease-in-out infinite;
}
.orb1 { width: 500px; height: 500px; background: rgba(0,200,255,0.04); top: -150px; right: -100px; animation-delay: 0s; }
.orb2 { width: 400px; height: 400px; background: rgba(0,255,136,0.03); bottom: 100px; left: -150px; animation-delay: -4s; }

@keyframes float {
  0%, 100% { transform: translateY(0px) scale(1); }
  50% { transform: translateY(-30px) scale(1.05); }
}

/* Layout */
.wrapper {
  max-width: 920px;
  margin: 0 auto;
  padding: 60px 24px 100px;
  position: relative;
  z-index: 1;
}

/* Fade-in animation */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(28px); }
  to { opacity: 1; transform: translateY(0); }
}

.animate { opacity: 0; animation: fadeUp 0.7s cubic-bezier(0.22,1,0.36,1) forwards; }
.d1 { animation-delay: 0.1s; }
.d2 { animation-delay: 0.2s; }
.d3 { animation-delay: 0.35s; }
.d4 { animation-delay: 0.5s; }
.d5 { animation-delay: 0.65s; }
.d6 { animation-delay: 0.8s; }
.d7 { animation-delay: 0.95s; }

/* ── HERO ── */
.hero {
  position: relative;
  padding: 56px 52px;
  background: var(--s1);
  border: 1px solid var(--border);
  border-radius: 20px;
  margin-bottom: 20px;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background: 
    radial-gradient(ellipse 60% 40% at 85% 20%, rgba(0,200,255,0.06) 0%, transparent 60%),
    radial-gradient(ellipse 40% 60% at 10% 90%, rgba(0,255,136,0.04) 0%, transparent 60%);
  pointer-events: none;
}

/* Corner accent lines */
.hero::after {
  content: '';
  position: absolute;
  top: 0; right: 0;
  width: 120px; height: 120px;
  border-top: 2px solid rgba(0,200,255,0.2);
  border-right: 2px solid rgba(0,200,255,0.2);
  border-radius: 0 20px 0 0;
  pointer-events: none;
}

.hero-inner { position: relative; z-index: 1; }

.avail-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(0,255,136,0.08);
  border: 1px solid rgba(0,255,136,0.2);
  border-radius: 100px;
  padding: 5px 14px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--green);
  letter-spacing: 0.05em;
  margin-bottom: 28px;
}

.avail-dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: var(--green);
  box-shadow: 0 0 10px var(--green);
  animation: blink 1.8s ease-in-out infinite;
}
@keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0.3;} }

.hero-top {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 24px;
  margin-bottom: 28px;
}

.hero-name-block {}

.hero-eyebrow {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--cyan);
  letter-spacing: 0.25em;
  text-transform: uppercase;
  margin-bottom: 10px;
  opacity: 0.8;
}

.hero-name {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(52px, 8vw, 80px);
  line-height: 0.95;
  letter-spacing: 0.01em;
  background: linear-gradient(135deg, #ffffff 0%, #a8c4d4 60%, var(--cyan) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 4px;
}

.hero-role {
  font-size: 14px;
  font-weight: 300;
  color: var(--muted2);
  letter-spacing: 0.05em;
  font-family: 'JetBrains Mono', monospace;
}

.hero-meta {
  display: flex;
  flex-direction: column;
  gap: 10px;
  align-items: flex-end;
}

.meta-item {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--muted);
  letter-spacing: 0.05em;
  display: flex;
  align-items: center;
  gap: 8px;
}
.meta-item span { color: var(--muted2); }

.hero-bio {
  font-size: 15px;
  font-weight: 300;
  color: #8fa5b8;
  line-height: 1.9;
  max-width: 580px;
  margin-bottom: 32px;
  border-left: 2px solid rgba(0,200,255,0.2);
  padding-left: 20px;
}
.hero-bio strong { color: var(--cyan); font-weight: 500; }

.connect-row {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.cbtn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 9px 18px;
  border-radius: 8px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  font-weight: 500;
  text-decoration: none;
  border: 1px solid transparent;
  cursor: pointer;
  transition: all 0.25s ease;
  position: relative;
  overflow: hidden;
}
.cbtn::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0;
  transition: opacity 0.25s;
}
.cbtn:hover::before { opacity: 1; }
.cbtn:hover { transform: translateY(-3px); box-shadow: 0 8px 24px rgba(0,0,0,0.4); }

.cbtn-portfolio {
  background: rgba(0,200,255,0.08);
  border-color: rgba(0,200,255,0.25);
  color: var(--cyan);
}
.cbtn-portfolio:hover { border-color: var(--cyan); box-shadow: 0 8px 24px rgba(0,200,255,0.15) !important; }

.cbtn-linkedin {
  background: rgba(10,102,194,0.1);
  border-color: rgba(10,102,194,0.3);
  color: #60a5fa;
}
.cbtn-linkedin:hover { border-color: #60a5fa; }

.cbtn-instagram {
  background: rgba(228,64,95,0.08);
  border-color: rgba(228,64,95,0.25);
  color: #fb7185;
}
.cbtn-instagram:hover { border-color: #fb7185; }

.cbtn-email {
  background: rgba(255,183,0,0.07);
  border-color: rgba(255,183,0,0.2);
  color: var(--amber);
}
.cbtn-email:hover { border-color: var(--amber); }

/* ── DIVIDER LABEL ── */
.section-header {
  display: flex;
  align-items: center;
  gap: 14px;
  margin-bottom: 18px;
  margin-top: 32px;
}
.section-header-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--border), transparent);
}
.section-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  font-weight: 500;
  color: var(--muted);
  letter-spacing: 0.3em;
  text-transform: uppercase;
  white-space: nowrap;
}
.section-num {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: var(--cyan);
  opacity: 0.6;
}

/* ── QUICK STATS ── */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 14px;
  margin-bottom: 20px;
}

.stat-card {
  background: var(--s1);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 22px 18px;
  text-align: center;
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
}
.stat-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: var(--accent-color, var(--cyan));
  opacity: 0;
  transition: opacity 0.3s;
}
.stat-card:hover { border-color: var(--accent-color, var(--cyan)); transform: translateY(-4px); }
.stat-card:hover::after { opacity: 1; }
.stat-card:nth-child(1) { --accent-color: var(--cyan); }
.stat-card:nth-child(2) { --accent-color: var(--green); }
.stat-card:nth-child(3) { --accent-color: var(--amber); }
.stat-card:nth-child(4) { --accent-color: var(--rose); }

.stat-num {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 36px;
  line-height: 1;
  color: var(--accent-color, var(--cyan));
  display: block;
  margin-bottom: 6px;
}
.stat-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  color: var(--muted);
  letter-spacing: 0.2em;
  text-transform: uppercase;
}

/* ── TECH STACK ── */
.tech-card {
  background: var(--s1);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 28px 32px;
  margin-bottom: 20px;
}

.tech-category {
  margin-bottom: 22px;
}
.tech-category:last-child { margin-bottom: 0; }

.tech-cat-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: var(--muted);
  letter-spacing: 0.2em;
  text-transform: uppercase;
  margin-bottom: 12px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.tech-cat-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

.tech-chips {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.chip {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 7px 14px;
  background: var(--s2);
  border: 1px solid var(--border);
  border-radius: 8px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--text);
  transition: all 0.25s;
  cursor: default;
  position: relative;
}
.chip:hover {
  background: var(--s3);
  border-color: var(--chip-color, var(--cyan));
  color: var(--chip-color, var(--cyan));
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.3);
}
.chip-dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--chip-color, var(--cyan));
  flex-shrink: 0;
  box-shadow: 0 0 6px var(--chip-color, var(--cyan));
}

/* ── PROJECTS ── */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
  margin-bottom: 20px;
}

.project-card {
  background: var(--s1);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 26px 28px;
  position: relative;
  overflow: hidden;
  cursor: default;
  transition: all 0.3s ease;
}

.project-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: var(--p-color, var(--cyan));
  opacity: 0.6;
  transition: opacity 0.3s;
}

.project-card:hover {
  border-color: var(--p-color, var(--cyan));
  transform: translateY(-5px);
  box-shadow: 0 16px 40px rgba(0,0,0,0.4);
}
.project-card:hover::before { opacity: 1; }

.project-card:nth-child(1) { --p-color: var(--cyan); }
.project-card:nth-child(2) { --p-color: var(--green); }
.project-card:nth-child(3) { --p-color: var(--amber); }
.project-card:nth-child(4) { --p-color: var(--rose); }

.p-icon {
  font-size: 28px;
  margin-bottom: 14px;
  display: block;
}

.p-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  color: var(--p-color, var(--cyan));
  letter-spacing: 0.2em;
  text-transform: uppercase;
  margin-bottom: 8px;
  opacity: 0.8;
}

.p-title {
  font-family: 'Outfit', sans-serif;
  font-size: 18px;
  font-weight: 600;
  color: #fff;
  margin-bottom: 10px;
  letter-spacing: -0.01em;
}

.p-desc {
  font-size: 13px;
  color: var(--muted2);
  line-height: 1.7;
  font-weight: 300;
  margin-bottom: 16px;
}

.p-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.p-badge {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  padding: 3px 9px;
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  border-radius: 4px;
  color: var(--muted2);
}

/* ── GITHUB STATS SECTION ── */
.github-stats-wrap {
  background: var(--s1);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 32px;
  margin-bottom: 20px;
}

.gh-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--muted);
  letter-spacing: 0.2em;
  text-transform: uppercase;
  margin-bottom: 22px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.gh-title::after { content: ''; flex: 1; height: 1px; background: var(--border); }

.gh-imgs {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 14px;
  margin-bottom: 14px;
}
.gh-imgs img, .gh-streak img {
  width: 100%;
  border-radius: 10px;
  border: 1px solid var(--border);
  display: block;
  transition: border-color 0.3s;
}
.gh-imgs img:hover, .gh-streak img:hover { border-color: var(--border2); }

/* ── ACTIVITY / SKILLS BARS ── */
.skills-section {
  background: var(--s1);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 32px;
  margin-bottom: 20px;
}

.skill-row {
  margin-bottom: 18px;
}
.skill-row:last-child { margin-bottom: 0; }

.skill-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 7px;
}
.skill-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--muted2);
}
.skill-pct {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--muted);
}

.skill-track {
  height: 3px;
  background: var(--s3);
  border-radius: 2px;
  overflow: hidden;
}

.skill-bar {
  height: 100%;
  border-radius: 2px;
  background: var(--bar-color, var(--cyan));
  box-shadow: 0 0 8px var(--bar-color, var(--cyan));
  animation: growBar 1.2s cubic-bezier(0.22,1,0.36,1) forwards;
  transform-origin: left;
  animation-delay: var(--bar-delay, 0s);
  width: 0%;
}

@keyframes growBar {
  to { width: var(--bar-width, 70%); }
}

/* ── FOOTER CTA ── */
.footer-cta {
  background: linear-gradient(135deg, var(--s1) 0%, var(--s2) 100%);
  border: 1px solid var(--border2);
  border-radius: 16px;
  padding: 44px 52px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.footer-cta::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse 70% 60% at 50% 50%, rgba(0,200,255,0.05) 0%, transparent 70%);
  pointer-events: none;
}

.cta-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: var(--cyan);
  letter-spacing: 0.3em;
  text-transform: uppercase;
  margin-bottom: 14px;
  opacity: 0.7;
}

.cta-heading {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(36px, 6vw, 56px);
  background: linear-gradient(135deg, #fff 0%, var(--cyan) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 16px;
  line-height: 1;
}

.cta-sub {
  font-size: 14px;
  color: var(--muted2);
  font-weight: 300;
  max-width: 420px;
  margin: 0 auto 28px;
  line-height: 1.7;
}

.cta-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 14px 32px;
  background: var(--cyan);
  color: #000;
  border-radius: 10px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s;
  box-shadow: 0 4px 30px rgba(0,200,255,0.25);
}
.cta-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 40px rgba(0,200,255,0.4);
  background: #33d4ff;
}

/* ── MISC ── */
.two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }

.info-card {
  background: var(--s1);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 26px 28px;
}

.info-card-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: var(--muted);
  letter-spacing: 0.2em;
  text-transform: uppercase;
  margin-bottom: 18px;
}

.focus-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 0;
  border-bottom: 1px solid var(--border);
  font-size: 13px;
  color: var(--muted2);
  font-weight: 300;
}
.focus-item:last-child { border-bottom: none; padding-bottom: 0; }
.focus-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--cyan); flex-shrink: 0; }

.quote-block {
  padding: 24px 28px;
  background: var(--s2);
  border-left: 3px solid var(--cyan);
  border-radius: 0 12px 12px 0;
  font-size: 14px;
  color: var(--muted2);
  font-style: italic;
  font-weight: 300;
  line-height: 1.8;
  margin-bottom: 0;
}
.quote-attr {
  margin-top: 10px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: var(--muted);
  letter-spacing: 0.1em;
  font-style: normal;
}

/* Scrollbar */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--bg); }
::-webkit-scrollbar-thumb { background: var(--s3); border-radius: 2px; }

@media (max-width: 640px) {
  .hero { padding: 32px 24px; }
  .hero-top { flex-direction: column; }
  .hero-meta { align-items: flex-start; }
  .stats-grid { grid-template-columns: repeat(2, 1fr); }
  .projects-grid { grid-template-columns: 1fr; }
  .two-col { grid-template-columns: 1fr; }
  .gh-imgs { grid-template-columns: 1fr; }
  .footer-cta { padding: 32px 24px; }
}
</style>
</head>
<body>

<!-- Cursor -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- Stars -->
<div class="stars" id="stars"></div>

<!-- Orbs -->
<div class="orb orb1"></div>
<div class="orb orb2"></div>

<div class="wrapper">

  <!-- ── HERO ── -->
  <section class="hero animate d1">
    <div class="hero-inner">
      <div class="avail-badge">
        <span class="avail-dot"></span>
        Open to Internships &amp; Collaborations
      </div>

      <div class="hero-top">
        <div class="hero-name-block">
          <div class="hero-eyebrow">// Full Stack &amp; Android Developer</div>
          <h1 class="hero-name">Pushwin<br>T H</h1>
          <div class="hero-role">pushwinth@gmail.com</div>
        </div>
        <div class="hero-meta">
          <div class="meta-item">📍 <span>India</span></div>
          <div class="meta-item">🎓 <span>Aspiring Software Dev</span></div>
          <div class="meta-item">💡 <span>IoT · Web · Android</span></div>
          <div class="meta-item">⚡ <span>Real-world builder</span></div>
        </div>
      </div>

      <p class="hero-bio">
        Passionate developer crafting <strong>full-stack web apps</strong> and <strong>Android applications</strong>
        that solve real problems. I thrive at the intersection of design and engineering — from 
        <strong>IoT systems</strong> to <strong>AI-integrated tools</strong> and <strong>real-time platforms</strong>.
        Building things that matter, one commit at a time.
      </p>

      <div class="connect-row">
        <a href="https://pushwin.github.io/pushwin-portfolio/" class="cbtn cbtn-portfolio" target="_blank">
          ◈ Portfolio
        </a>
        <a href="https://linkedin.com/in/pushwin" class="cbtn cbtn-linkedin" target="_blank">
          ↗ LinkedIn
        </a>
        <a href="https://www.instagram.com/push_win_gowda" class="cbtn cbtn-instagram" target="_blank">
          ◉ Instagram
        </a>
        <a href="mailto:pushwinth@gmail.com" class="cbtn cbtn-email">
          ✉ Email Me
        </a>
      </div>
    </div>
  </section>

  <!-- ── QUICK STATS ── -->
  <div class="stats-grid animate d2">
    <div class="stat-card">
      <span class="stat-num">4+</span>
      <span class="stat-label">Major Projects</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">9</span>
      <span class="stat-label">Technologies</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">AI</span>
      <span class="stat-label">ML Integration</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">∞</span>
      <span class="stat-label">Growth Mindset</span>
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="section-header animate d2">
    <span class="section-num">01</span>
    <span class="section-title">Tech Arsenal</span>
    <div class="section-header-line"></div>
  </div>

  <div class="tech-card animate d3">
    <div class="tech-category">
      <div class="tech-cat-label">Languages</div>
      <div class="tech-chips">
        <span class="chip" style="--chip-color:#ED8B00"><span class="chip-dot"></span>Java</span>
        <span class="chip" style="--chip-color:#7F52FF"><span class="chip-dot"></span>Kotlin</span>
        <span class="chip" style="--chip-color:#F7DF1E"><span class="chip-dot"></span>JavaScript</span>
        <span class="chip" style="--chip-color:#3178C6"><span class="chip-dot"></span>TypeScript</span>
        <span class="chip" style="--chip-color:#E34F26"><span class="chip-dot"></span>HTML5</span>
        <span class="chip" style="--chip-color:#1572B6"><span class="chip-dot"></span>CSS3</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-cat-label">Databases &amp; Cloud</div>
      <div class="tech-chips">
        <span class="chip" style="--chip-color:#FFCA28"><span class="chip-dot"></span>Firebase</span>
        <span class="chip" style="--chip-color:#4479A1"><span class="chip-dot"></span>MySQL</span>
        <span class="chip" style="--chip-color:#47A248"><span class="chip-dot"></span>MongoDB</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-cat-label">Tools &amp; Platforms</div>
      <div class="tech-chips">
        <span class="chip" style="--chip-color:#F05032"><span class="chip-dot"></span>Git</span>
        <span class="chip" style="--chip-color:#00c8ff"><span class="chip-dot"></span>Android Studio</span>
        <span class="chip" style="--chip-color:#007ACC"><span class="chip-dot"></span>VS Code</span>
        <span class="chip" style="--chip-color:#ff6b6b"><span class="chip-dot"></span>WebSockets</span>
        <span class="chip" style="--chip-color:#7ee787"><span class="chip-dot"></span>REST APIs</span>
      </div>
    </div>
  </div>

  <!-- ── SKILL PROFICIENCY ── -->
  <div class="two-col animate d3" style="margin-bottom:20px;">
    <div class="skills-section" style="border-radius:16px;margin-bottom:0;">
      <div class="gh-title" style="margin-bottom:22px;">Proficiency</div>

      <div class="skill-row">
        <div class="skill-info">
          <span class="skill-name">Android / Kotlin</span>
          <span class="skill-pct">88%</span>
        </div>
        <div class="skill-track">
          <div class="skill-bar" style="--bar-width:88%;--bar-color:#7F52FF;--bar-delay:0.1s;"></div>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-info">
          <span class="skill-name">JavaScript / TypeScript</span>
          <span class="skill-pct">82%</span>
        </div>
        <div class="skill-track">
          <div class="skill-bar" style="--bar-width:82%;--bar-color:#F7DF1E;--bar-delay:0.2s;"></div>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-info">
          <span class="skill-name">Java</span>
          <span class="skill-pct">85%</span>
        </div>
        <div class="skill-track">
          <div class="skill-bar" style="--bar-width:85%;--bar-color:#ED8B00;--bar-delay:0.3s;"></div>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-info">
          <span class="skill-name">Firebase / MySQL</span>
          <span class="skill-pct">78%</span>
        </div>
        <div class="skill-track">
          <div class="skill-bar" style="--bar-width:78%;--bar-color:#FFCA28;--bar-delay:0.4s;"></div>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-info">
          <span class="skill-name">IoT / Embedded</span>
          <span class="skill-pct">70%</span>
        </div>
        <div class="skill-track">
          <div class="skill-bar" style="--bar-width:70%;--bar-color:#00ff88;--bar-delay:0.5s;"></div>
        </div>
      </div>
    </div>

    <div class="info-card">
      <div class="info-card-title">Current Focus</div>
      <div class="focus-item"><span class="focus-dot"></span>Full Stack Web Development</div>
      <div class="focus-item"><span class="focus-dot" style="background:var(--green)"></span>Android & Kotlin Mastery</div>
      <div class="focus-item"><span class="focus-dot" style="background:var(--amber)"></span>AI / ML Integration in Apps</div>
      <div class="focus-item"><span class="focus-dot" style="background:var(--rose)"></span>Cloud Architecture & Firebase</div>
      <div class="focus-item"><span class="focus-dot" style="background:#7F52FF"></span>Open Source Contributions</div>
      <div style="margin-top:20px;">
        <div class="quote-block">
          "Code is not just syntax — it's a conversation with the future."
          <div class="quote-attr">— Pushwin T H</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ── PROJECTS ── -->
  <div class="section-header animate d4">
    <span class="section-num">02</span>
    <span class="section-title">Major Projects</span>
    <div class="section-header-line"></div>
  </div>

  <div class="projects-grid animate d4">
    <div class="project-card">
      <span class="p-icon">🧠</span>
      <div class="p-tag">Web App · AI</div>
      <h3 class="p-title">Grammar Checker</h3>
      <p class="p-desc">AI + rule-based grammar correction platform with multi-model integration. Supports real-time suggestions, context-aware fixes, and NLP-powered tone analysis.</p>
      <div class="p-tags">
        <span class="p-badge">JavaScript</span>
        <span class="p-badge">NLP</span>
        <span class="p-badge">REST API</span>
        <span class="p-badge">AI Models</span>
      </div>
    </div>

    <div class="project-card">
      <span class="p-icon">🎵</span>
      <div class="p-tag">Web App · Real-time</div>
      <h3 class="p-title">Music Sync App</h3>
      <p class="p-desc">Real-time synchronized music playback across multiple devices using WebSockets. Sub-100ms sync latency with room-based session management.</p>
      <div class="p-tags">
        <span class="p-badge">WebSockets</span>
        <span class="p-badge">Node.js</span>
        <span class="p-badge">Real-time</span>
        <span class="p-badge">TypeScript</span>
      </div>
    </div>

    <div class="project-card">
      <span class="p-icon">🌾</span>
      <div class="p-tag">Android · Marketplace</div>
      <h3 class="p-title">AgriMarketplace</h3>
      <p class="p-desc">Android app connecting farmers directly to buyers, eliminating intermediaries. Features live pricing, geo-based listings, and Firebase-backed inventory management.</p>
      <div class="p-tags">
        <span class="p-badge">Kotlin</span>
        <span class="p-badge">Firebase</span>
        <span class="p-badge">Android</span>
        <span class="p-badge">MySQL</span>
      </div>
    </div>

    <div class="project-card">
      <span class="p-icon">⛑️</span>
      <div class="p-tag">IoT · Safety</div>
      <h3 class="p-title">Smart Helmet</h3>
      <p class="p-desc">IoT-based accident detection and emergency alert system. Detects impact via sensors, auto-sends GPS location to emergency contacts with real-time monitoring dashboard.</p>
      <div class="p-tags">
        <span class="p-badge">IoT</span>
        <span class="p-badge">GPS</span>
        <span class="p-badge">Java</span>
        <span class="p-badge">Sensors</span>
      </div>
    </div>
  </div>

  <!-- ── GITHUB STATS ── -->
  <div class="section-header animate d5">
    <span class="section-num">03</span>
    <span class="section-title">GitHub Activity</span>
    <div class="section-header-line"></div>
  </div>

  <div class="github-stats-wrap animate d5">
    <div class="gh-title">Live Stats</div>
    <div class="gh-imgs">
      <img src="https://github-readme-stats.vercel.app/api?username=Pushwin&show_icons=true&theme=tokyonight&bg_color=0b0e1a&border_color=1e2740&title_color=00c8ff&icon_color=00ff88&text_color=8fa5b8&hide_border=false" alt="Pushwin GitHub Stats" />
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Pushwin&layout=compact&theme=tokyonight&bg_color=0b0e1a&border_color=1e2740&title_color=00c8ff&text_color=8fa5b8" alt="Top Languages" />
    </div>
    <div class="gh-streak">
      <img src="https://streak-stats.demolab.com/?user=Pushwin&theme=tokyonight&background=0b0e1a&border=1e2740&stroke=00c8ff&ring=00c8ff&fire=ff4d6d&currStreakNum=ffffff&sideNums=8fa5b8&currStreakLabel=00c8ff&sideLabels=8fa5b8&dates=4a5568" alt="GitHub Streak" />
    </div>
  </div>

  <!-- ── FOOTER CTA ── -->
  <div class="footer-cta animate d6">
    <div class="cta-label">// Let's Build Together</div>
    <h2 class="cta-heading">Ready to Collaborate?</h2>
    <p class="cta-sub">Open to internships, entry-level opportunities, and exciting side projects. Let's turn ideas into impactful software.</p>
    <a href="mailto:pushwinth@gmail.com" class="cta-btn">
      ✉ Get In Touch
    </a>
  </div>

</div>

<script>
  // Stars
  const starsEl = document.getElementById('stars');
  for (let i = 0; i < 120; i++) {
    const s = document.createElement('span');
    const size = Math.random() * 2 + 0.5;
    s.style.cssText = `
      width:${size}px;height:${size}px;
      left:${Math.random()*100}%;
      top:${Math.random()*100}%;
      --d:${2+Math.random()*4}s;
      --delay:${Math.random()*5}s;
      --op:${0.2+Math.random()*0.5};
    `;
    starsEl.appendChild(s);
  }

  // Cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let rx = 0, ry = 0, mx = 0, my = 0;
  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.left = mx+'px';
    cursor.style.top = my+'px';
  });
  function animRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx+'px';
    ring.style.top = ry+'px';
    requestAnimationFrame(animRing);
  }
  animRing();

  document.querySelectorAll('a, button, .chip, .stat-card, .project-card').forEach(el => {
    el.addEventListener('mouseenter', () => {
      ring.style.transform = 'translate(-50%,-50%) scale(1.6)';
      ring.style.borderColor = 'rgba(0,200,255,0.6)';
    });
    el.addEventListener('mouseleave', () => {
      ring.style.transform = 'translate(-50%,-50%) scale(1)';
      ring.style.borderColor = 'rgba(0,200,255,0.3)';
    });
  });
</script>
</body>
</html>
