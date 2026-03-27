<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vansh Bansal — AI Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Sora:wght@300;400;500;600&family=JetBrains+Mono:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #03070f;
  --surface: #080f1c;
  --surface2: #0c1628;
  --accent: #00e5ff;
  --accent2: #7c3aed;
  --accent3: #f43f5e;
  --gold: #fbbf24;
  --green: #10b981;
  --text: #e2eaf5;
  --muted: #4a6080;
  --muted2: #7a90a8;
  --border: rgba(0,229,255,0.10);
  --border2: rgba(124,58,237,0.15);
  --glow-c: 0 0 30px rgba(0,229,255,0.18);
  --glow-p: 0 0 30px rgba(124,58,237,0.18);
  --glow-r: 0 0 20px rgba(244,63,94,0.15);
  --glow-g: 0 0 20px rgba(16,185,129,0.15);
}
*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:'Sora',sans-serif;min-height:100vh;overflow-x:hidden}

/* ── Noise grain overlay ── */
body::after{content:'';position:fixed;inset:0;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");pointer-events:none;z-index:999;opacity:0.6}

/* ── Grid ── */
body::before{content:'';position:fixed;inset:0;background:linear-gradient(rgba(0,229,255,0.025) 1px,transparent 1px),linear-gradient(90deg,rgba(0,229,255,0.025) 1px,transparent 1px);background-size:56px 56px;pointer-events:none;z-index:0}

/* ── Blobs ── */
.blob{position:fixed;border-radius:50%;filter:blur(120px);pointer-events:none;z-index:0}
.b1{width:600px;height:600px;background:rgba(124,58,237,0.10);top:-150px;right:-150px}
.b2{width:450px;height:450px;background:rgba(0,229,255,0.07);bottom:-100px;left:-100px}
.b3{width:350px;height:350px;background:rgba(244,63,94,0.06);top:60%;left:35%}

.wrap{position:relative;z-index:1;max-width:940px;margin:0 auto;padding:0 24px 100px}

/* ════════════════════════════
   HERO
════════════════════════════ */
.hero{text-align:center;padding:72px 0 56px;position:relative}
.hero-tag{
  display:inline-flex;align-items:center;gap:8px;
  font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:3px;color:var(--accent);
  text-transform:uppercase;padding:6px 16px;border:1px solid var(--border);border-radius:100px;
  background:rgba(0,229,255,0.05);margin-bottom:28px;
  opacity:0;animation:fadeUp .5s .1s forwards
}
.hero-tag::before{content:'';width:6px;height:6px;border-radius:50%;background:var(--accent);box-shadow:0 0 8px var(--accent)}
.hero-name{
  font-family:'Orbitron',sans-serif;
  font-size:clamp(42px,8vw,84px);font-weight:900;line-height:0.95;
  letter-spacing:-1px;
  background:linear-gradient(135deg,#fff 0%,var(--accent) 55%,var(--accent2) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  margin-bottom:20px;
  opacity:0;animation:fadeUp .6s .25s forwards
}
.hero-sub{
  font-size:15px;color:var(--muted2);font-weight:400;letter-spacing:.3px;
  opacity:0;animation:fadeUp .5s .4s forwards;margin-bottom:28px
}
.hero-meta{
  display:flex;justify-content:center;gap:20px;flex-wrap:wrap;margin-bottom:36px;
  opacity:0;animation:fadeUp .5s .52s forwards
}
.meta-chip{
  display:flex;align-items:center;gap:7px;font-size:12px;color:var(--muted2);
  font-family:'JetBrains Mono',monospace;letter-spacing:.5px
}
.meta-chip a{color:var(--accent);text-decoration:none}
.meta-chip a:hover{text-decoration:underline}
.hero-divider{
  width:240px;height:1px;margin:0 auto 28px;
  background:linear-gradient(90deg,transparent,var(--accent),var(--accent2),transparent);
  opacity:0;animation:fadeIn .6s .65s forwards
}
.hero-quote{
  font-size:13px;color:var(--muted);font-style:italic;letter-spacing:.4px;
  opacity:0;animation:fadeUp .5s .75s forwards
}

/* ════════════════════════════
   SECTION HEADING SYSTEM
════════════════════════════ */
.sec{margin-bottom:64px}
.sec-head{display:flex;align-items:center;gap:14px;margin-bottom:32px}
.sec-num{
  font-family:'Orbitron',monospace;font-size:11px;font-weight:700;
  color:var(--accent2);letter-spacing:2px;flex-shrink:0
}
/* THE ACTUAL HEADING — visually prominent */
h2.sec-title{
  font-family:'Orbitron',sans-serif;
  font-size:clamp(18px,3vw,22px);
  font-weight:700;
  letter-spacing:1.5px;
  text-transform:uppercase;
  color:#fff;
  flex-shrink:0;
  line-height:1
}
.sec-line{flex:1;height:1px;background:linear-gradient(90deg,var(--border),transparent)}

/* Sub-headings inside cards */
h3.card-title{
  font-family:'Orbitron',sans-serif;
  font-size:13px;font-weight:700;letter-spacing:.8px;
  color:var(--text);margin-bottom:6px;line-height:1.3
}
h4.item-title{
  font-family:'Sora',sans-serif;
  font-size:13px;font-weight:600;color:var(--text);
  margin-bottom:4px;line-height:1.4
}

/* ════════════════════════════
   CARDS
════════════════════════════ */
.card{
  background:var(--surface);border:1px solid var(--border);
  border-radius:16px;padding:24px 28px;position:relative;overflow:hidden;
  transition:border-color .25s,box-shadow .25s,transform .25s
}
.card:hover{border-color:rgba(0,229,255,0.28);box-shadow:var(--glow-c);transform:translateY(-2px)}
.card-accent-top::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--accent2),var(--accent),var(--accent3))}
.card-accent-left::before{content:'';position:absolute;top:0;left:0;bottom:0;width:2px;background:linear-gradient(180deg,var(--accent2),var(--accent))}

/* ════════════════════════════
   ABOUT / PROFILE SUMMARY
════════════════════════════ */
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.about-item{display:flex;align-items:flex-start;gap:12px;padding:14px;background:var(--surface2);border-radius:10px;border:1px solid var(--border)}
.about-icon{font-size:20px;flex-shrink:0;margin-top:2px}
.about-label{font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:2px;color:var(--accent);text-transform:uppercase;margin-bottom:5px}
.about-val{font-size:13px;color:var(--text);font-weight:500;line-height:1.5}
.about-sub{font-size:11px;color:var(--muted2);margin-top:3px;line-height:1.5}

.summary-text{
  font-size:13px;color:var(--muted2);line-height:1.8;margin-bottom:20px;
  border-left:2px solid var(--accent2);padding-left:16px
}

/* ════════════════════════════
   LIVE GITHUB STATS
════════════════════════════ */
.gh-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:14px}
.gh-card{background:var(--surface);border:1px solid var(--border2);border-radius:14px;padding:22px 24px;position:relative;overflow:hidden}
.gh-card::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--accent2),transparent)}
.gh-label{font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:2px;color:var(--accent2);text-transform:uppercase;margin-bottom:16px;display:flex;align-items:center;gap:8px}
.gh-label::before{content:'';width:5px;height:5px;border-radius:50%;background:var(--accent2);box-shadow:0 0 8px var(--accent2)}
.gh-stat-row{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px}
.gh-key{font-size:12px;color:var(--muted2)}
.gh-val{font-family:'Orbitron',sans-serif;font-size:15px;font-weight:700;color:var(--text)}
.gh-val.live{color:var(--accent)}
.bar-wrap{height:4px;background:rgba(255,255,255,0.05);border-radius:2px;margin:4px 0 12px;overflow:hidden}
.bar-fill{height:100%;border-radius:2px;transition:width 1.2s cubic-bezier(.4,0,.2,1)}
.loading-pulse{animation:pulse 1.5s ease-in-out infinite}
@keyframes pulse{0%,100%{opacity:.4}50%{opacity:1}}
.live-badge{display:inline-flex;align-items:center;gap:5px;font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--green);letter-spacing:1px;padding:3px 8px;border:1px solid rgba(16,185,129,.25);border-radius:100px;background:rgba(16,185,129,.06)}
.live-badge::before{content:'';width:5px;height:5px;border-radius:50%;background:var(--green);animation:blink 1.2s ease infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.2}}

/* streak row */
.streak-row{background:var(--surface);border:1px solid var(--border2);border-radius:14px;padding:24px 28px;display:flex;align-items:center;justify-content:space-around;flex-wrap:wrap;gap:20px;box-shadow:var(--glow-p)}
.st-item{text-align:center}
.st-num{font-family:'Orbitron',sans-serif;font-size:clamp(26px,4vw,38px);font-weight:900;background:linear-gradient(135deg,var(--accent),var(--accent2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.st-label{font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:2px;color:var(--muted);text-transform:uppercase;margin-top:4px}
.st-div{width:1px;height:52px;background:var(--border)}

/* ════════════════════════════
   TECH STACK
════════════════════════════ */
.stack-cat-label{font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:2px;color:var(--accent2);text-transform:uppercase;margin-bottom:10px;margin-top:20px}
.stack-cat-label:first-child{margin-top:0}
.stack-chips{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:4px}
.chip{
  font-family:'JetBrains Mono',monospace;font-size:11px;
  padding:6px 14px;border-radius:8px;
  border:1px solid var(--border);background:rgba(0,229,255,0.04);
  color:var(--text);letter-spacing:.5px;
  transition:border-color .2s,box-shadow .2s,transform .2s;cursor:default
}
.chip:hover{border-color:var(--accent);box-shadow:var(--glow-c);transform:translateY(-1px);color:var(--accent)}
.chip.expert{border-color:rgba(16,185,129,.2);color:var(--green)}
.chip.advanced{border-color:rgba(0,229,255,.15);color:var(--accent)}

/* ════════════════════════════
   WORK EXP
════════════════════════════ */
.exp-card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:22px 26px;margin-bottom:12px;position:relative;overflow:hidden}
.exp-card::before{content:'';position:absolute;left:0;top:0;bottom:0;width:2px;background:linear-gradient(180deg,var(--accent),var(--accent2))}
.exp-header{display:flex;justify-content:space-between;align-items:flex-start;gap:12px;margin-bottom:4px;flex-wrap:wrap}
.exp-company{font-family:'Orbitron',sans-serif;font-size:13px;font-weight:700;color:var(--accent);letter-spacing:.5px}
.exp-period{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--muted2);letter-spacing:1px;flex-shrink:0;padding:3px 10px;border:1px solid var(--border);border-radius:100px}
.exp-role{font-size:12px;color:var(--muted2);margin-bottom:12px;font-style:italic}
.exp-bullets{list-style:none;display:flex;flex-direction:column;gap:7px}
.exp-bullets li{font-size:12px;color:var(--muted2);line-height:1.7;padding-left:16px;position:relative}
.exp-bullets li::before{content:'▹';position:absolute;left:0;color:var(--accent);font-size:10px;top:1px}

/* ════════════════════════════
   PROJECTS
════════════════════════════ */
.proj-card{
  background:var(--surface);border:1px solid var(--border);border-radius:14px;
  padding:22px 26px;margin-bottom:12px;position:relative;overflow:hidden;
  transition:border-color .25s,box-shadow .25s,transform .25s
}
.proj-card:hover{border-color:var(--accent);box-shadow:var(--glow-c);transform:translateY(-2px)}
.proj-top{display:flex;justify-content:space-between;align-items:flex-start;gap:12px;flex-wrap:wrap;margin-bottom:8px}
.proj-name-wrap{display:flex;align-items:center;gap:10px}
.proj-emoji{font-size:22px}
.proj-period{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:1px;padding:3px 10px;border:1px solid var(--border);border-radius:100px;flex-shrink:0}
.proj-stat-badge{font-family:'Orbitron',sans-serif;font-size:13px;font-weight:700;color:var(--accent);padding:4px 12px;background:rgba(0,229,255,0.07);border:1px solid rgba(0,229,255,0.15);border-radius:8px;flex-shrink:0}
.proj-desc{font-size:12px;color:var(--muted2);line-height:1.7;margin-bottom:10px}
.proj-tags{display:flex;flex-wrap:wrap;gap:6px}
.proj-tag{font-family:'JetBrains Mono',monospace;font-size:9px;padding:3px 9px;border-radius:5px;background:rgba(124,58,237,0.08);border:1px solid rgba(124,58,237,0.2);color:var(--accent2);letter-spacing:1px}

/* ════════════════════════════
   RESEARCH & PATENTS
════════════════════════════ */
.research-card{
  background:var(--surface);border:1px solid rgba(124,58,237,0.18);
  border-radius:14px;padding:22px 26px;margin-bottom:12px;
  position:relative;overflow:hidden;
  transition:border-color .25s,box-shadow .25s,transform .25s
}
.research-card:hover{border-color:var(--accent2);box-shadow:var(--glow-p);transform:translateX(4px)}
.research-card::before{content:'';position:absolute;left:0;top:0;bottom:0;width:3px;background:linear-gradient(180deg,var(--accent2),var(--accent3))}
.research-type{font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:2px;text-transform:uppercase;margin-bottom:8px;display:inline-flex;align-items:center;gap:6px}
.badge{padding:3px 10px;border-radius:100px;font-size:9px;font-family:'JetBrains Mono',monospace;letter-spacing:1px;display:inline-block}
.badge-acc{background:rgba(16,185,129,.1);border:1px solid rgba(16,185,129,.25);color:var(--green)}
.badge-pub{background:rgba(0,229,255,.08);border:1px solid rgba(0,229,255,.2);color:var(--accent)}
.badge-pat{background:rgba(251,191,36,.08);border:1px solid rgba(251,191,36,.25);color:var(--gold)}
.badge-pend{background:rgba(244,63,94,.08);border:1px solid rgba(244,63,94,.2);color:var(--accent3)}
.research-publisher{font-size:11px;color:var(--muted);margin-top:4px;font-style:italic}
.research-desc{font-size:12px;color:var(--muted2);line-height:1.7;margin-top:8px}

/* ════════════════════════════
   CERTS
════════════════════════════ */
.cert-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:10px}
.cert-item{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:14px 16px;display:flex;align-items:flex-start;gap:10px;transition:border-color .2s,transform .2s}
.cert-item:hover{border-color:var(--gold);transform:translateY(-1px);box-shadow:0 0 16px rgba(251,191,36,.1)}
.cert-icon{font-size:18px;flex-shrink:0}
.cert-name{font-size:11px;font-weight:600;color:var(--text);line-height:1.4;margin-bottom:3px}
.cert-org{font-size:10px;color:var(--muted);font-family:'JetBrains Mono',monospace;letter-spacing:.5px}

/* ════════════════════════════
   ACHIEVEMENTS
════════════════════════════ */
.ach-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(210px,1fr));gap:10px}
.ach-card{background:var(--surface);border:1px solid rgba(251,191,36,.12);border-radius:12px;padding:16px 18px;display:flex;align-items:flex-start;gap:12px;transition:border-color .2s,box-shadow .2s,transform .2s}
.ach-card:hover{border-color:var(--gold);box-shadow:0 0 20px rgba(251,191,36,.12);transform:translateY(-2px)}
.ach-icon{font-size:22px;flex-shrink:0}
.ach-name{font-size:12px;font-weight:600;color:var(--text);margin-bottom:4px}
.ach-desc{font-size:11px;color:var(--muted2);line-height:1.5}

/* ════════════════════════════
   EDUCATION
════════════════════════════ */
.edu-card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:20px 24px;margin-bottom:10px;display:flex;gap:16px;align-items:flex-start}
.edu-dot-wrap{display:flex;flex-direction:column;align-items:center;gap:4px;flex-shrink:0;margin-top:4px}
.edu-dot{width:10px;height:10px;border-radius:50%;background:var(--accent);box-shadow:0 0 10px var(--accent)}
.edu-line{width:1px;height:30px;background:var(--border)}
.edu-deg{font-family:'Orbitron',sans-serif;font-size:12px;font-weight:700;color:var(--text);margin-bottom:4px;letter-spacing:.3px}
.edu-inst{font-size:12px;color:var(--accent);margin-bottom:4px}
.edu-meta{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--muted2);letter-spacing:.5px}
.edu-cgpa{display:inline-flex;align-items:center;gap:6px;font-family:'Orbitron',sans-serif;font-size:12px;font-weight:700;color:var(--gold);margin-top:6px}

/* ════════════════════════════
   CONTACT
════════════════════════════ */
.contact-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:10px}
.contact-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:16px 20px;display:flex;align-items:center;gap:14px;text-decoration:none;transition:border-color .2s,box-shadow .2s,transform .2s;color:inherit}
.contact-card:hover{border-color:var(--accent);box-shadow:var(--glow-c);transform:translateY(-2px)}
.contact-icon{font-size:22px;flex-shrink:0}
.contact-label{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:2px;text-transform:uppercase;margin-bottom:4px}
.contact-val{font-size:12px;color:var(--text);font-weight:500;word-break:break-all}

/* ════════════════════════════
   FOOTER
════════════════════════════ */
.footer{text-align:center;padding:40px 0 20px;border-top:1px solid var(--border);margin-top:60px}
.footer-txt{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--muted);letter-spacing:3px;text-transform:uppercase}
.footer-glow{width:160px;height:1px;background:linear-gradient(90deg,transparent,var(--accent),var(--accent2),transparent);margin:14px auto 0}

/* ════════════════════════════
   ANIMATIONS
════════════════════════════ */
@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
.fade{opacity:0;transform:translateY(18px);transition:opacity .6s,transform .6s}
.fade.visible{opacity:1;transform:translateY(0)}

/* ════════════════════════════
   RESPONSIVE
════════════════════════════ */
@media(max-width:640px){
  .about-grid,.gh-grid{grid-template-columns:1fr}
  .st-div{display:none}
  .proj-top{flex-direction:column}
  .exp-header{flex-direction:column}
  .streak-row{gap:16px}
}
</style>
</head>
<body>
<div class="blob b1"></div>
<div class="blob b2"></div>
<div class="blob b3"></div>
<div class="wrap">

<!-- ══════════ HERO ══════════ -->
<header class="hero">
  <div class="hero-tag">AI &amp; ML Engineer · Open to Opportunities</div>
  <h1 class="hero-name">VANSH<br>BANSAL</h1>
  <p class="hero-sub">B.E. CSE (AI &amp; ML) · Chandigarh University · CGPA 8.65</p>
  <div class="hero-meta">
    <span class="meta-chip">📍 Mohali, Punjab</span>
    <span class="meta-chip">📞 +91 75280-24936</span>
    <span class="meta-chip">✉️ <a href="mailto:vansh.nitubansal@gmail.com">vansh.nitubansal@gmail.com</a></span>
    <span class="meta-chip">🔗 <a href="https://www.linkedin.com/in/vansh-bansal-92b335271/" target="_blank">LinkedIn</a></span>
    <span class="meta-chip">🐙 <a href="https://github.com/VanshBansal-1104" target="_blank">GitHub</a></span>
  </div>
  <div class="hero-divider"></div>
  <p class="hero-quote">"Building intelligent systems that transform data into impactful decisions."</p>
</header>

<!-- ══════════ PROFILE SUMMARY ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">01</span>
    <h2 class="sec-title">Profile Summary</h2>
    <div class="sec-line"></div>
  </div>
  <div class="card card-accent-top">
    <p class="summary-text">Analytical and results-driven Data Analyst &amp; AI Engineer with hands-on experience leveraging Python, SQL, machine learning, and statistical analysis to solve real-world business problems. Proficient in data cleaning, EDA, feature engineering, and model development — with a proven ability to transform complex datasets into actionable insights. Strong foundation in AI-driven analytics and data visualisation, with a passion for contributing to data-informed decision-making and high-impact projects.</p>
    <div class="about-grid">
      <div class="about-item">
        <div class="about-icon">🎓</div>
        <div><div class="about-label">Education</div><div class="about-val">B.E. CSE (Hons.) — AI &amp; ML</div><div class="about-sub">Chandigarh University · 2023–2027</div></div>
      </div>
      <div class="about-item">
        <div class="about-icon">📊</div>
        <div><div class="about-label">Academic Standing</div><div class="about-val">CGPA: 8.65 / 10</div><div class="about-sub">Specialization in AI &amp; Machine Learning</div></div>
      </div>
      <div class="about-item">
        <div class="about-icon">🧠</div>
        <div><div class="about-label">Core Domains</div><div class="about-val">NLP · Computer Vision · MLOps</div><div class="about-sub">ETL Pipelines · EDA · Statistical Analysis</div></div>
      </div>
      <div class="about-item">
        <div class="about-icon">📄</div>
        <div><div class="about-label">Research Output</div><div class="about-val">2 Publications · 1 Patent Filed</div><div class="about-sub">Assistive Tech &amp; Healthcare AI</div></div>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ LIVE GITHUB STATS ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">02</span>
    <h2 class="sec-title">GitHub Analytics</h2>
    <div class="sec-line"></div>
    <span class="live-badge">LIVE</span>
  </div>

  <div class="gh-grid">
    <div class="gh-card">
      <div class="gh-label">Repository Stats</div>
      <div class="gh-stat-row"><span class="gh-key">Public Repos</span><span class="gh-val live loading-pulse" id="repos">—</span></div>
      <div class="gh-stat-row"><span class="gh-key">Total Stars</span><span class="gh-val live loading-pulse" id="stars">—</span></div>
      <div class="gh-stat-row"><span class="gh-key">Followers</span><span class="gh-val live loading-pulse" id="followers">—</span></div>
      <div class="gh-stat-row"><span class="gh-key">Following</span><span class="gh-val live loading-pulse" id="following">—</span></div>
      <div style="margin-top:14px">
        <div style="font-size:10px;color:var(--muted);letter-spacing:1px;font-family:'JetBrains Mono',monospace;margin-bottom:5px">PROFILE COMPLETENESS</div>
        <div class="bar-wrap"><div class="bar-fill" id="prog-bar" style="width:0%;background:linear-gradient(90deg,var(--accent),var(--accent2))"></div></div>
      </div>
    </div>

    <div class="gh-card">
      <div class="gh-label">Top Languages</div>
      <div>
        <div class="gh-stat-row" style="margin-bottom:3px"><span class="gh-key">Python</span><span style="font-size:11px;color:var(--accent);font-family:'JetBrains Mono',monospace">65%</span></div>
        <div class="bar-wrap"><div class="bar-fill" style="width:0%;background:#3776AB" data-width="65"></div></div>
      </div>
      <div>
        <div class="gh-stat-row" style="margin-bottom:3px"><span class="gh-key">JavaScript</span><span style="font-size:11px;color:var(--accent);font-family:'JetBrains Mono',monospace">15%</span></div>
        <div class="bar-wrap"><div class="bar-fill" style="width:0%;background:#F7DF1E" data-width="15"></div></div>
      </div>
      <div>
        <div class="gh-stat-row" style="margin-bottom:3px"><span class="gh-key">C++</span><span style="font-size:11px;color:var(--accent);font-family:'JetBrains Mono',monospace">12%</span></div>
        <div class="bar-wrap"><div class="bar-fill" style="width:0%;background:#00599C" data-width="12"></div></div>
      </div>
      <div>
        <div class="gh-stat-row" style="margin-bottom:3px"><span class="gh-key">HTML / CSS</span><span style="font-size:11px;color:var(--accent);font-family:'JetBrains Mono',monospace">8%</span></div>
        <div class="bar-wrap"><div class="bar-fill" style="width:0%;background:#E34F26" data-width="8"></div></div>
      </div>
      <div id="lang-status" style="margin-top:12px;font-size:10px;font-family:'JetBrains Mono',monospace;color:var(--muted);letter-spacing:1px">LOADING LANGUAGES...</div>
    </div>
  </div>

  <!-- Streak / summary row -->
  <div class="streak-row">
    <div class="st-item"><div class="st-num loading-pulse" id="st-repos">—</div><div class="st-label">Public Repos</div></div>
    <div class="st-div"></div>
    <div class="st-item"><div class="st-num loading-pulse" id="st-stars">—</div><div class="st-label">Total Stars</div></div>
    <div class="st-div"></div>
    <div class="st-item"><div class="st-num loading-pulse" id="st-followers">—</div><div class="st-label">Followers</div></div>
    <div class="st-div"></div>
    <div class="st-item"><div class="st-num">8.65</div><div class="st-label">CGPA</div></div>
    <div class="st-div"></div>
    <div class="st-item"><div class="st-num">3</div><div class="st-label">Pub. &amp; Patents</div></div>
  </div>
</section>

<!-- ══════════ TECH STACK ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">03</span>
    <h2 class="sec-title">Tech Stack</h2>
    <div class="sec-line"></div>
  </div>
  <div class="card card-accent-top">
    <div class="stack-cat-label">Programming Languages</div>
    <div class="stack-chips">
      <span class="chip expert">Python ★</span>
      <span class="chip advanced">C++</span>
      <span class="chip advanced">C</span>
      <span class="chip advanced">Golang</span>
      <span class="chip advanced">JavaScript</span>
    </div>
    <div class="stack-cat-label">AI / ML &amp; Data</div>
    <div class="stack-chips">
      <span class="chip expert">Scikit-learn ★</span>
      <span class="chip expert">NLP / NLTK / spaCy ★</span>
      <span class="chip advanced">OpenCV</span>
      <span class="chip advanced">Pandas</span>
      <span class="chip advanced">Feature Engineering</span>
      <span class="chip advanced">EDA</span>
      <span class="chip advanced">ETL Pipelines</span>
      <span class="chip advanced">A/B Testing</span>
      <span class="chip advanced">Statistical Analysis</span>
    </div>
    <div class="stack-cat-label">Databases &amp; Visualisation</div>
    <div class="stack-chips">
      <span class="chip expert">SQL / MySQL ★</span>
      <span class="chip expert">Power BI ★</span>
      <span class="chip advanced">Excel</span>
      <span class="chip advanced">RDBMS</span>
      <span class="chip advanced">Business Intelligence</span>
    </div>
    <div class="stack-cat-label">Web &amp; Dev Tools</div>
    <div class="stack-chips">
      <span class="chip advanced">Flask</span>
      <span class="chip advanced">HTML / CSS</span>
      <span class="chip advanced">Flutter</span>
      <span class="chip advanced">Figma / UI·UX</span>
      <span class="chip advanced">Git &amp; GitHub</span>
      <span class="chip advanced">IBM Cloud</span>
      <span class="chip advanced">Azure AI</span>
    </div>
    <div style="margin-top:16px;font-size:10px;color:var(--muted);font-family:'JetBrains Mono',monospace;letter-spacing:1px">★ = Expert &nbsp;·&nbsp; Cyan = Advanced</div>
  </div>
</section>

<!-- ══════════ WORK EXPERIENCE ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">04</span>
    <h2 class="sec-title">Work Experience</h2>
    <div class="sec-line"></div>
  </div>
  <div class="exp-card">
    <div class="exp-header">
      <div>
        <div class="exp-company">Edunet Foundation</div>
        <div class="exp-role">Data Analytics Intern (Remote) · India</div>
      </div>
      <span class="exp-period">Jul 2024 – Aug 2024</span>
    </div>
    <ul class="exp-bullets">
      <li>Applied data cleaning, preprocessing, and exploratory data analysis (EDA) to analyse datasets using Python, SQL, statistical methods, and feature engineering.</li>
      <li>Built and evaluated analytical and predictive models using standard performance metrics, while monitoring KPIs to assess system performance and user engagement for 200+ active users.</li>
    </ul>
  </div>
</section>

<!-- ══════════ PROJECTS ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">05</span>
    <h2 class="sec-title">Featured Projects</h2>
    <div class="sec-line"></div>
  </div>

  <div class="proj-card">
    <div class="proj-top">
      <div class="proj-name-wrap">
        <span class="proj-emoji">🎯</span>
        <h3 class="card-title">PrepVel</h3>
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center">
        <span class="proj-period">Jan 2026 – Present</span>
        <span class="proj-stat-badge">Active ▲</span>
      </div>
    </div>
    <p class="proj-desc">Architected an AI-driven career platform for students and graduates, integrating resume analysis, mock interview feedback, job matching, and mentorship features.</p>
    <div class="proj-tags"><span class="proj-tag">Python</span><span class="proj-tag">NLP</span><span class="proj-tag">Flask</span><span class="proj-tag">MySQL</span><span class="proj-tag">JavaScript</span></div>
  </div>

  <div class="proj-card">
    <div class="proj-top">
      <div class="proj-name-wrap">
        <span class="proj-emoji">📊</span>
        <h3 class="card-title">Sales Data Dashboard</h3>
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center">
        <span class="proj-period">Jan 2025 – Jun 2025</span>
        <span class="proj-stat-badge">↓50% Manual Work</span>
      </div>
    </div>
    <p class="proj-desc">Expanded and automated interactive sales dashboards analysing 100K+ transactional records, enabling identification of 15–20% regional performance gaps and reducing manual reporting effort by 50%.</p>
    <div class="proj-tags"><span class="proj-tag">SQL</span><span class="proj-tag">Power BI</span><span class="proj-tag">Excel</span><span class="proj-tag">Statistical Analysis</span></div>
  </div>

  <div class="proj-card">
    <div class="proj-top">
      <div class="proj-name-wrap">
        <span class="proj-emoji">🧠</span>
        <h3 class="card-title">Sentiment Analysis System</h3>
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center">
        <span class="proj-period">Aug 2024 – Dec 2024</span>
        <span class="proj-stat-badge">85% Accuracy</span>
      </div>
    </div>
    <p class="proj-desc">Built, trained, and evaluated ML models for sentiment analysis — achieving 85% classification accuracy on 5,000+ customer feedback samples. Enabled sentiment-driven insights improving decision turnaround by ~30%.</p>
    <div class="proj-tags"><span class="proj-tag">Scikit-learn</span><span class="proj-tag">NLP</span><span class="proj-tag">Pandas</span><span class="proj-tag">Python</span></div>
  </div>

  <div class="proj-card">
    <div class="proj-top">
      <div class="proj-name-wrap">
        <span class="proj-emoji">🌍</span>
        <h3 class="card-title">Universal Translator</h3>
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center">
        <span class="proj-period">Jan 2024 – May 2024</span>
        <span class="proj-stat-badge">10+ Languages</span>
      </div>
    </div>
    <p class="proj-desc">Engineered a multi-language accessibility platform supporting voice, text, Braille, and basic sign language — enabling real-time translation across 10+ languages and improving accessibility usability scores by ~35%.</p>
    <div class="proj-tags"><span class="proj-tag">Computer Vision</span><span class="proj-tag">NLP</span><span class="proj-tag">OpenCV</span><span class="proj-tag">AI</span></div>
  </div>

  <div class="proj-card">
    <div class="proj-top">
      <div class="proj-name-wrap">
        <span class="proj-emoji">🌐</span>
        <h3 class="card-title">Portfolio Website</h3>
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center">
        <span class="proj-period">Dec 2023</span>
        <span class="proj-stat-badge">100% Mobile</span>
      </div>
    </div>
    <p class="proj-desc">Fully responsive personal portfolio website with optimised UI/UX, achieving 40% faster load times and 100% mobile responsiveness.</p>
    <div class="proj-tags"><span class="proj-tag">HTML</span><span class="proj-tag">CSS</span><span class="proj-tag">JavaScript</span><span class="proj-tag">UI/UX</span></div>
  </div>
</section>

<!-- ══════════ RESEARCH & PATENTS ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">06</span>
    <h2 class="sec-title">Research &amp; Patents</h2>
    <div class="sec-line"></div>
  </div>

  <div class="research-card">
    <div class="research-type" style="color:var(--accent)">
      <span>📄 Research Paper</span>
      <span class="badge badge-pub">PUBLISHED</span>
      <span class="badge badge-acc">~90% Accuracy</span>
    </div>
    <h3 class="card-title">VisionCane: AI-IoT Assistive Navigation System</h3>
    <div class="research-publisher">Published on Springer Nature Link</div>
    <p class="research-desc">Researched and prototyped an IoT-AI assistive framework for real-time object detection aimed at enhancing mobility and safety for visually impaired users. Achieved ~90% detection accuracy using computer vision models integrated with edge IoT hardware.</p>
  </div>

  <div class="research-card">
    <div class="research-type" style="color:var(--accent3)">
      <span>📄 Research Paper</span>
      <span class="badge badge-pub">PUBLISHED</span>
      <span class="badge badge-acc">~92% Accuracy</span>
    </div>
    <h3 class="card-title">AI in Ophthalmology: Early Eye Disease Detection</h3>
    <div class="research-publisher">Published in IJSRD (International Journal for Scientific Research &amp; Development)</div>
    <p class="research-desc">Authored and published a research study on AI-based early detection of eye diseases, benchmarking models with up to 92% diagnostic accuracy and proposing cost-efficient screening workflows suitable for underserved healthcare environments.</p>
  </div>

  <div class="research-card" style="border-color:rgba(251,191,36,0.2)">
    <div class="research-type" style="color:var(--gold)">
      <span>⚖️ Patent</span>
      <span class="badge badge-pat">APPLICATION NO: 202611002036</span>
      <span class="badge badge-pend">PENDING</span>
    </div>
    <h3 class="card-title">Intelligent Online System for Structured Access &amp; Retrieval of Academic Question Papers</h3>
    <div class="research-publisher">Indian Patent Office · Filed 2026</div>
    <p class="research-desc">Novel AI-driven system for intelligent classification, indexing, and retrieval of academic question papers — enabling structured access, smart search, and citation recommendations for educational institutions.</p>
  </div>
</section>

<!-- ══════════ ACHIEVEMENTS ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">07</span>
    <h2 class="sec-title">Achievements &amp; Leadership</h2>
    <div class="sec-line"></div>
  </div>
  <div class="ach-grid">
    <div class="ach-card"><div class="ach-icon">🏆</div><div><div class="ach-name">AlgoVerse 2025 Finalist</div><div class="ach-desc">HackWithIndia — National algorithmic problem-solving competition</div></div></div>
    <div class="ach-card"><div class="ach-icon">💡</div><div><div class="ach-name">Ideat-A-Thon Finalist</div><div class="ach-desc">National-level innovation &amp; product ideation challenge</div></div></div>
    <div class="ach-card"><div class="ach-icon">👑</div><div><div class="ach-name">Head of Partnership &amp; Finance</div><div class="ach-desc">Apex Techno Warriors Society — University Level leadership</div></div></div>
    <div class="ach-card"><div class="ach-icon">⭐</div><div><div class="ach-name">CGPA 8.65 / 10</div><div class="ach-desc">Academic excellence in AI &amp; ML specialization</div></div></div>
  </div>
</section>

<!-- ══════════ CERTIFICATIONS ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">08</span>
    <h2 class="sec-title">Certifications</h2>
    <div class="sec-line"></div>
  </div>
  <div class="cert-grid">
    <div class="cert-item"><div class="cert-icon">☁️</div><div><div class="cert-name">Azure AI Fundamentals</div><div class="cert-org">Microsoft Certified</div></div></div>
    <div class="cert-item"><div class="cert-icon">🌐</div><div><div class="cert-name">Cloud Application Development</div><div class="cert-org">IBM</div></div></div>
    <div class="cert-item"><div class="cert-icon">🗄️</div><div><div class="cert-name">Structured Query Language</div><div class="cert-org">Oracle</div></div></div>
    <div class="cert-item"><div class="cert-icon">🐙</div><div><div class="cert-name">GitHub Foundations</div><div class="cert-org">GitHub</div></div></div>
    <div class="cert-item"><div class="cert-icon">🐍</div><div><div class="cert-name">Python for Data Science, AI &amp; Dev</div><div class="cert-org">IBM / Coursera</div></div></div>
    <div class="cert-item"><div class="cert-icon">💼</div><div><div class="cert-name">Virtual Job Simulations</div><div class="cert-org">Forage · SWE &amp; Data Analytics</div></div></div>
  </div>
</section>

<!-- ══════════ EDUCATION ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">09</span>
    <h2 class="sec-title">Education</h2>
    <div class="sec-line"></div>
  </div>
  <div class="edu-card">
    <div class="edu-dot-wrap"><div class="edu-dot"></div><div class="edu-line"></div></div>
    <div style="flex:1">
      <div class="edu-deg">B.E. CSE (Hons.) — Artificial Intelligence &amp; Machine Learning</div>
      <div class="edu-inst">Chandigarh University, Punjab</div>
      <div class="edu-meta">Jul 2023 – May 2027</div>
      <div class="edu-cgpa">⭐ CGPA: 8.65 / 10</div>
    </div>
  </div>
  <div class="edu-card">
    <div class="edu-dot-wrap"><div class="edu-dot" style="background:var(--accent2);box-shadow:0 0 10px var(--accent2)"></div></div>
    <div style="flex:1">
      <div class="edu-deg">Intermediate (11th – 12th)</div>
      <div class="edu-inst">Government Model Senior Secondary School, Sector 37-B, Chandigarh</div>
      <div class="edu-meta">Aug 2021 – Mar 2023</div>
    </div>
  </div>
</section>

<!-- ══════════ CONTACT ══════════ -->
<section class="sec fade">
  <div class="sec-head">
    <span class="sec-num">10</span>
    <h2 class="sec-title">Connect</h2>
    <div class="sec-line"></div>
  </div>
  <div class="contact-grid">
    <a class="contact-card" href="https://www.linkedin.com/in/vansh-bansal-92b335271/" target="_blank">
      <div class="contact-icon">💼</div>
      <div><div class="contact-label">LinkedIn</div><div class="contact-val">vansh-bansal-92b335271</div></div>
    </a>
    <a class="contact-card" href="mailto:vansh.nitubansal@gmail.com">
      <div class="contact-icon">📧</div>
      <div><div class="contact-label">Email</div><div class="contact-val">vansh.nitubansal@gmail.com</div></div>
    </a>
    <a class="contact-card" href="https://github.com/VanshBansal-1104" target="_blank">
      <div class="contact-icon">🐙</div>
      <div><div class="contact-label">GitHub</div><div class="contact-val">VanshBansal-1104</div></div>
    </a>
    <div class="contact-card" style="cursor:default">
      <div class="contact-icon">📞</div>
      <div><div class="contact-label">Phone</div><div class="contact-val">+91 75280-24936</div></div>
    </div>
  </div>
</section>

<!-- ══════════ FOOTER ══════════ -->
<footer class="footer">
  <div class="footer-txt">Vansh Bansal · AI Engineer · Chandigarh University · 2025</div>
  <div class="footer-glow"></div>
</footer>

</div><!-- /wrap -->

<script>
// ── Scroll-triggered fade-in ──
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('visible') });
}, { threshold: 0.08 });
document.querySelectorAll('.fade').forEach(el => observer.observe(el));

// ── Animate language bars on load ──
setTimeout(() => {
  document.querySelectorAll('.bar-fill[data-width]').forEach(bar => {
    bar.style.width = bar.dataset.width + '%';
  });
},400);

// ── Live GitHub Stats ──
async function fetchGitHub() {
  try {
    const res = await fetch('https://api.github.com/users/VanshBansal-1104', {
      headers: { 'Accept': 'application/vnd.github.v3+json' }
    });
    if (!res.ok) throw new Error('API error');
    const d = await res.json();

    const repos = d.public_repos ?? '—';
    const followers = d.followers ?? '—';
    const following = d.following ?? '—';

    // Fetch stars separately
    let stars = 0;
    try {
      const repoRes = await fetch('https://api.github.com/users/VanshBansal-1104/repos?per_page=100');
      const repoData = await repoRes.json();
      if (Array.isArray(repoData)) {
        stars = repoData.reduce((s, r) => s + (r.stargazers_count || 0), 0);

        // Real language breakdown
        const langMap = {};
        repoData.forEach(r => { if(r.language) langMap[r.language] = (langMap[r.language]||0)+1; });
        const total = Object.values(langMap).reduce((a,b)=>a+b,0);
        if(total > 0) {
          const sorted = Object.entries(langMap).sort((a,b)=>b[1]-a[1]);
          document.getElementById('lang-status').textContent = 'LIVE FROM GITHUB API ✓';
          document.getElementById('lang-status').style.color = 'var(--green)';
          // update bars if top languages differ
          const langBars = document.querySelectorAll('.bar-fill[data-width]');
          const langLabels = ['Python','JavaScript','C++','HTML / CSS'];
          sorted.slice(0,4).forEach((entry,i) => {
            const pct = Math.round((entry[1]/total)*100);
            if(langBars[i]) {
              langBars[i].style.width = pct+'%';
              langBars[i].closest('div').previousElementSibling.querySelector('span:last-child').textContent = pct+'%';
              langBars[i].closest('div').previousElementSibling.querySelector('span:first-child').textContent = entry[0];
            }
          });
        }
      }
    } catch(_) {}

    // Remove pulse from live fields
    ['repos','stars','followers','following','st-repos','st-stars','st-followers'].forEach(id => {
      const el = document.getElementById(id);
      if(el) el.classList.remove('loading-pulse');
    });

    animateCount('repos', repos);
    animateCount('stars', stars);
    animateCount('followers', followers);
    animateCount('following', following);
    animateCount('st-repos', repos);
    animateCount('st-stars', stars);
    animateCount('st-followers', followers);

    // Progress bar based on completeness
    const prog = Math.min(100, Math.round((repos/20)*100));
    document.getElementById('prog-bar').style.width = prog + '%';

  } catch(err) {
    // Graceful fallback — show last-known values
    const fallback = { repos:'20+', stars:'10+', followers:'15+', following:'10+' };
    Object.entries(fallback).forEach(([k,v]) => {
      ['','st-'].forEach(p => {
        const el = document.getElementById(p+k);
        if(el) { el.textContent = v; el.classList.remove('loading-pulse'); }
      });
    });
    document.getElementById('lang-status').textContent = 'CACHED DATA (API LIMIT)';
    document.getElementById('prog-bar').style.width = '70%';
  }
}

function animateCount(id, target) {
  const el = document.getElementById(id);
  if(!el) return;
  const num = parseInt(target) || 0;
  if(num === 0){ el.textContent = target; return; }
  let current = 0;
  const step = Math.max(1, Math.floor(num / 40));
  const timer = setInterval(() => {
    current = Math.min(current + step, num);
    el.textContent = current;
    if(current >= num) clearInterval(timer);
  }, 30);
}

fetchGitHub();
</script>
</body>
</html>
