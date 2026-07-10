<!DOCTYPE html>  <html lang="en">  
<head>  
  <meta charset="UTF-8" />  
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
  <title>Yaswanth K — Frontend Developer</title>  
  <link rel="preconnect" href="https://fonts.googleapis.com"/>  
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet"/>  
  <style>  
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }  :root {  
  --bg:       #0b0d11;  
  --surface:  #13161d;  
  --border:   #1e2330;  
  --accent:   #4ff7c8;  
  --accent2:  #7b5cf6;  
  --text:     #e8eaf0;  
  --muted:    #6b7280;  
  --mono:     'JetBrains Mono', monospace;  
  --sans:     'Space Grotesk', sans-serif;  
}  

html { scroll-behavior: smooth; }  

body {  
  background: var(--bg);  
  color: var(--text);  
  font-family: var(--sans);  
  font-size: 16px;  
  line-height: 1.6;  
  overflow-x: hidden;  
}  

/* ── SCROLLBAR ── */  
::-webkit-scrollbar { width: 4px; }  
::-webkit-scrollbar-track { background: var(--bg); }  
::-webkit-scrollbar-thumb { background: var(--accent2); border-radius: 2px; }  

/* ── NOISE OVERLAY ── */  
body::before {  
  content: '';  
  position: fixed; inset: 0;  
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");  
  pointer-events: none; z-index: 0; opacity: .4;  
}  

/* ── NAV ── */  
nav {  
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;  
  display: flex; justify-content: space-between; align-items: center;  
  padding: 1.2rem 6vw;  
  backdrop-filter: blur(14px);  
  background: rgba(11,13,17,.75);  
  border-bottom: 1px solid var(--border);  
}  
.nav-logo {  
  font-family: var(--mono);  
  font-size: .85rem;  
  color: var(--accent);  
  letter-spacing: .08em;  
}  
.nav-links { display: flex; gap: 2rem; list-style: none; }  
.nav-links a {  
  text-decoration: none; color: var(--muted);  
  font-size: .875rem; font-weight: 500;  
  transition: color .2s;  
}  
.nav-links a:hover { color: var(--accent); }  

/* ── HERO ── */  
#hero {  
  min-height: 100vh;  
  display: flex; align-items: center;  
  padding: 0 6vw;  
  position: relative;  
}  
.hero-glow {  
  position: absolute; top: 20%; left: 50%;  
  width: 700px; height: 700px;  
  transform: translate(-50%,-50%);  
  background: radial-gradient(ellipse at center, rgba(79,247,200,.07) 0%, transparent 70%);  
  pointer-events: none;  
}  
.hero-inner { position: relative; max-width: 780px; }  
.hero-eyebrow {  
  font-family: var(--mono);  
  font-size: .8rem; color: var(--accent);  
  letter-spacing: .2em; text-transform: uppercase;  
  margin-bottom: 1.5rem;  
  display: flex; align-items: center; gap: .7rem;  
}  
.hero-eyebrow::before {  
  content: ''; display: inline-block;  
  width: 32px; height: 1px;  
  background: var(--accent);  
}  
h1 {  
  font-size: clamp(3rem, 8vw, 6.5rem);  
  font-weight: 700;  
  line-height: 1.0;  
  letter-spacing: -.03em;  
  margin-bottom: 1.5rem;  
}  
h1 .name-accent { color: var(--accent); }  
.hero-sub {  
  font-size: clamp(1rem, 2.5vw, 1.25rem);  
  color: var(--muted);  
  max-width: 520px;  
  margin-bottom: 2.5rem;  
  line-height: 1.7;  
}  
.hero-cta { display: flex; gap: 1rem; flex-wrap: wrap; }  
.btn-primary {  
  display: inline-flex; align-items: center; gap: .5rem;  
  padding: .8rem 2rem;  
  background: var(--accent);  
  color: #0b0d11;  
  font-weight: 700; font-size: .9rem;  
  border-radius: 4px;  
  text-decoration: none;  
  transition: opacity .2s, transform .15s;  
}  
.btn-primary:hover { opacity: .85; transform: translateY(-1px); }  
.btn-outline {  
  display: inline-flex; align-items: center; gap: .5rem;  
  padding: .8rem 2rem;  
  border: 1px solid var(--border);  
  color: var(--text);  
  font-weight: 500; font-size: .9rem;  
  border-radius: 4px;  
  text-decoration: none;  
  transition: border-color .2s, color .2s;  
}  
.btn-outline:hover { border-color: var(--accent); color: var(--accent); }  

.hero-stats {  
  display: flex; gap: 3rem; margin-top: 4rem;  
  flex-wrap: wrap;  
}  
.stat-num {  
  font-size: 2rem; font-weight: 700; color: var(--accent);  
  font-family: var(--mono);  
  line-height: 1;  
}  
.stat-label { font-size: .78rem; color: var(--muted); margin-top: .3rem; text-transform: uppercase; letter-spacing: .1em; }  

/* ── SECTIONS ── */  
section { padding: 7rem 6vw; position: relative; }  
.section-label {  
  font-family: var(--mono); font-size: .75rem;  
  color: var(--accent2); letter-spacing: .2em;  
  text-transform: uppercase; margin-bottom: .75rem;  
}  
h2 {  
  font-size: clamp(1.8rem, 4vw, 2.6rem);  
  font-weight: 700; letter-spacing: -.02em;  
  margin-bottom: 1rem;  
}  
.section-intro { color: var(--muted); max-width: 540px; margin-bottom: 3.5rem; }  

/* ── ABOUT ── */  
#about { border-top: 1px solid var(--border); }  
.about-grid {  
  display: grid;  
  grid-template-columns: 1fr 1fr;  
  gap: 4rem;  
  align-items: start;  
}  
.about-text p { color: var(--muted); line-height: 1.8; margin-bottom: 1rem; }  
.about-details {  
  display: flex; flex-direction: column; gap: 1.25rem;  
}  
.detail-row {  
  display: flex; align-items: center; gap: 1rem;  
  padding: 1rem 1.25rem;  
  background: var(--surface);  
  border: 1px solid var(--border);  
  border-radius: 8px;  
}  
.detail-icon { font-size: 1.2rem; }  
.detail-label { font-size: .75rem; color: var(--muted); text-transform: uppercase; letter-spacing: .08em; }  
.detail-val { font-size: .95rem; font-weight: 500; }  

/* ── SKILLS ── */  
#skills { background: var(--surface); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }  
.skills-grid {  
  display: grid;  
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));  
  gap: 1.5rem;  
}  
.skill-card {  
  background: var(--bg);  
  border: 1px solid var(--border);  
  border-radius: 10px;  
  padding: 1.5rem;  
  transition: border-color .2s, transform .15s;  
}  
.skill-card:hover { border-color: var(--accent); transform: translateY(-2px); }  
.skill-card-title {  
  font-size: .7rem; color: var(--accent2);  
  text-transform: uppercase; letter-spacing: .15em;  
  margin-bottom: 1rem;  
}  
.skill-tags { display: flex; flex-wrap: wrap; gap: .5rem; }  
.tag {  
  font-family: var(--mono); font-size: .75rem;  
  padding: .3rem .7rem;  
  background: var(--surface);  
  border: 1px solid var(--border);  
  border-radius: 4px; color: var(--text);  
}  
.tag.accent { border-color: var(--accent); color: var(--accent); background: rgba(79,247,200,.06); }  

/* ── EXPERIENCE ── */  
#experience { border-top: 1px solid var(--border); }  
.exp-card {  
  background: var(--surface);  
  border: 1px solid var(--border);  
  border-left: 3px solid var(--accent);  
  border-radius: 10px;  
  padding: 2rem;  
  max-width: 760px;  
}  
.exp-header { display: flex; justify-content: space-between; flex-wrap: wrap; gap: .5rem; margin-bottom: 1rem; }  
.exp-role { font-size: 1.15rem; font-weight: 600; }  
.exp-company { color: var(--accent); }  
.exp-period { font-family: var(--mono); font-size: .78rem; color: var(--muted); align-self: center; }  
.exp-list { list-style: none; display: flex; flex-direction: column; gap: .6rem; }  
.exp-list li { color: var(--muted); font-size: .9rem; padding-left: 1.2rem; position: relative; }  
.exp-list li::before { content: '▸'; position: absolute; left: 0; color: var(--accent); }  

/* ── PROJECTS ── */  
#projects { background: var(--surface); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }  
.projects-grid {  
  display: grid;  
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));  
  gap: 1.5rem;  
}  
.project-card {  
  background: var(--bg);  
  border: 1px solid var(--border);  
  border-radius: 12px;  
  padding: 2rem;  
  display: flex; flex-direction: column;  
  gap: 1rem;  
  transition: border-color .2s, transform .15s;  
  position: relative; overflow: hidden;  
}  
.project-card::before {  
  content: '';  
  position: absolute; top: 0; left: 0; right: 0; height: 2px;  
  background: linear-gradient(90deg, var(--accent), var(--accent2));  
  opacity: 0; transition: opacity .2s;  
}  
.project-card:hover { border-color: var(--accent2); transform: translateY(-3px); }  
.project-card:hover::before { opacity: 1; }  
.project-num {  
  font-family: var(--mono); font-size: .7rem;  
  color: var(--accent2); letter-spacing: .15em;  
}  
.project-title { font-size: 1.1rem; font-weight: 600; line-height: 1.3; }  
.project-desc { color: var(--muted); font-size: .875rem; line-height: 1.7; flex: 1; }  
.project-stack { display: flex; flex-wrap: wrap; gap: .4rem; }  

/* ── ACHIEVEMENTS ── */  
#achievements { border-top: 1px solid var(--border); }  
.ach-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }  
.ach-card {  
  background: var(--surface);  
  border: 1px solid var(--border);  
  border-radius: 10px;  
  padding: 1.5rem 1.75rem;  
  display: flex; gap: 1.25rem; align-items: flex-start;  
  transition: border-color .2s;  
}  
.ach-card:hover { border-color: var(--accent2); }  
.ach-icon { font-size: 1.75rem; flex-shrink: 0; margin-top: .1rem; }  
.ach-title { font-weight: 600; margin-bottom: .35rem; }  
.ach-desc { color: var(--muted); font-size: .875rem; line-height: 1.6; }  

/* ── CONTACT ── */  
#contact {  
  background: var(--surface);  
  border-top: 1px solid var(--border);  
  text-align: center;  
}  
#contact h2 { margin-bottom: 1rem; }  
#contact .section-intro { margin-inline: auto; text-align: center; }  
.contact-links {  
  display: flex; justify-content: center; flex-wrap: wrap;  
  gap: 1rem; margin-top: 2.5rem;  
}  
.contact-link {  
  display: inline-flex; align-items: center; gap: .6rem;  
  padding: .9rem 1.75rem;  
  border: 1px solid var(--border);  
  border-radius: 8px;  
  text-decoration: none; color: var(--text);  
  font-size: .9rem; font-weight: 500;  
  transition: border-color .2s, color .2s, background .2s;  
}  
.contact-link:hover { border-color: var(--accent); color: var(--accent); background: rgba(79,247,200,.04); }  
.contact-link .icon { font-size: 1rem; }  

/* ── FOOTER ── */  
footer {  
  padding: 2rem 6vw;  
  border-top: 1px solid var(--border);  
  display: flex; justify-content: space-between; align-items: center;  
  flex-wrap: wrap; gap: 1rem;  
}  
.footer-copy { font-size: .8rem; color: var(--muted); }  
.footer-mono { font-family: var(--mono); font-size: .75rem; color: var(--accent2); }  

/* ── CURSOR DOT ── */  
.cursor {  
  position: fixed; width: 8px; height: 8px;  
  background: var(--accent); border-radius: 50%;  
  pointer-events: none; z-index: 9999;  
  transform: translate(-50%,-50%);  
  transition: transform .1s, width .2s, height .2s, opacity .2s;  
}  

/* ── ANIMATIONS ── */  
.fade-up {  
  opacity: 0; transform: translateY(24px);  
  transition: opacity .6s ease, transform .6s ease;  
}  
.fade-up.visible { opacity: 1; transform: translateY(0); }  

/* ── RESPONSIVE ── */  
@media (max-width: 768px) {  
  nav { padding: 1rem 5vw; }  
  .nav-links { display: none; }  
  .about-grid { grid-template-columns: 1fr; gap: 2rem; }  
  .hero-stats { gap: 2rem; }  
  section { padding: 5rem 5vw; }  
}  

@media (prefers-reduced-motion: reduce) {  
  .fade-up { transition: none; }  
  .cursor { display: none; }  
}

  </style>  
</head>  
<body>  <div class="cursor" id="cursor"></div>  <!-- NAV -->  <nav>  
  <div class="nav-logo">YK.dev</div>  
  <ul class="nav-links">  
    <li><a href="#about">About</a></li>  
    <li><a href="#skills">Skills</a></li>  
    <li><a href="#experience">Experience</a></li>  
    <li><a href="#projects">Projects</a></li>  
    <li><a href="#contact">Contact</a></li>  
  </ul>  
</nav>  <!-- HERO -->  <section id="hero">  
  <div class="hero-glow"></div>  
  <div class="hero-inner">  
    <div class="hero-eyebrow">Frontend Developer</div>  
    <h1>  
      Building the<br/>  
      <span class="name-accent">web you see.</span>  
    </h1>  
    <p class="hero-sub">  
      I'm Yaswanth K — a CS undergrad passionate about crafting responsive,   
      full-stack web experiences using React, Node.js & MongoDB.  
    </p>  
    <div class="hero-cta">  
      <a href="#projects" class="btn-primary">View Projects ↓</a>  
      <a href="#contact" class="btn-outline">Get in Touch</a>  
    </div>  
    <div class="hero-stats">  
      <div>  
        <div class="stat-num">3+</div>  
        <div class="stat-label">Projects Built</div>  
      </div>  
      <div>  
        <div class="stat-num">5+</div>  
        <div class="stat-label">Technologies</div>  
      </div>  
      <div>  
        <div class="stat-num">1×</div>  
        <div class="stat-label">Hackathon Finalist</div>  
      </div>  
    </div>  
  </div>  
</section>  <!-- ABOUT -->  <section id="about">  
  <div class="fade-up">  
    <div class="section-label">// About me</div>  
    <h2>Who I Am</h2>  
  </div>  
  <div class="about-grid fade-up">  
    <div class="about-text">  
      <p>  
        I'm a final-year Computer Science student at Angel College of Engineering and Technology,   
        Tiruppur, graduating in 2026. I love turning ideas into real, working products on the web.  
      </p>  
      <p>  
        From hackathon stages to email campaign dashboards, I've worked across the stack —   
        writing clean React UIs, wiring up Express APIs, and managing MongoDB databases.   
        I'm always eager to pick up new tools and improve how I build.  
      </p>  
      <p>  
        Currently interning as an Email Marketing Intern at Xexnaro, where I'm sharpening   
        my data-driven thinking alongside my coding skills.  
      </p>  
    </div>  
    <div class="about-details">  
      <div class="detail-row">  
        <div class="detail-icon">🎓</div>  
        <div>  
          <div class="detail-label">Education</div>  
          <div class="detail-val">B.E CSE — Graduating 2026</div>  
        </div>  
      </div>  
      <div class="detail-row">  
        <div class="detail-icon">📍</div>  
        <div>  
          <div class="detail-label">Location</div>  
          <div class="detail-val">Tamil Nadu, India</div>  
        </div>  
      </div>  
      <div class="detail-row">  
        <div class="detail-icon">💼</div>  
        <div>  
          <div class="detail-label">Status</div>  
          <div class="detail-val">Open to Opportunities</div>  
        </div>  
      </div>  
      <div class="detail-row">  
        <div class="detail-icon">🗣️</div>  
        <div>  
          <div class="detail-label">Languages</div>  
          <div class="detail-val">English & Tamil</div>  
        </div>  
      </div>  
    </div>  
  </div>  
</section>  <!-- SKILLS -->  <section id="skills">  
  <div class="fade-up">  
    <div class="section-label">// Tech stack</div>  
    <h2>What I Work With</h2>  
    <p class="section-intro">A curated set of tools I use to build, ship, and maintain web applications.</p>  
  </div>  
  <div class="skills-grid fade-up">  
    <div class="skill-card">  
      <div class="skill-card-title">Frontend</div>  
      <div class="skill-tags">  
        <span class="tag accent">React.js</span>  
        <span class="tag accent">JavaScript</span>  
        <span class="tag">HTML</span>  
        <span class="tag">CSS</span>  
        <span class="tag">Tailwind CSS</span>  
      </div>  
    </div>  
    <div class="skill-card">  
      <div class="skill-card-title">Backend</div>  
      <div class="skill-tags">  
        <span class="tag accent">Node.js</span>  
        <span class="tag accent">Express.js</span>  
        <span class="tag">REST APIs</span>  
        <span class="tag">JWT Auth</span>  
        <span class="tag">Socket.io</span>  
      </div>  
    </div>  
    <div class="skill-card">  
      <div class="skill-card-title">Database</div>  
      <div class="skill-tags">  
        <span class="tag accent">MongoDB</span>  
        <span class="tag">SQL</span>  
        <span class="tag">Firebase</span>  
      </div>  
    </div>  
    <div class="skill-card">  
      <div class="skill-card-title">Languages</div>  
      <div class="skill-tags">  
        <span class="tag">Python</span>  
        <span class="tag">Java</span>  
        <span class="tag">C</span>  
        <span class="tag">SQL</span>  
      </div>  
    </div>  
    <div class="skill-card">  
      <div class="skill-card-title">Tools</div>  
      <div class="skill-tags">  
        <span class="tag accent">Git & GitHub</span>  
        <span class="tag">VS Code</span>  
        <span class="tag">Flutter</span>  
      </div>  
    </div>  
    <div class="skill-card">  
      <div class="skill-card-title">Soft Skills</div>  
      <div class="skill-tags">  
        <span class="tag">Team Work</span>  
        <span class="tag">Communication</span>  
        <span class="tag">Problem Solving</span>  
        <span class="tag">Adaptability</span>  
      </div>  
    </div>  
  </div>  
</section>  <!-- EXPERIENCE -->  <section id="experience">  
  <div class="fade-up">  
    <div class="section-label">// Work experience</div>  
    <h2>Where I've Worked</h2>  
    <p class="section-intro">Real-world experience building skills beyond the classroom.</p>  
  </div>  
  <div class="exp-card fade-up">  
    <div class="exp-header">  
      <div>  
        <div class="exp-role">Email Marketing Intern</div>  
        <div class="exp-company">Xexnaro (Remote)</div>  
      </div>  
      <div class="exp-period">Sep 2025 — Present</div>  
    </div>  
    <ul class="exp-list">  
      <li>Managed and executed email campaigns targeting diverse customer segments</li>  
      <li>Performed audience segmentation, A/B testing, and campaign scheduling to boost engagement</li>  
      <li>Analyzed performance metrics and generated reports to improve conversions</li>  
      <li>Collaborated on data-driven email marketing strategies with the team</li>  
    </ul>  
  </div>  
</section>  <!-- PROJECTS -->  <section id="projects">  
  <div class="fade-up">  
    <div class="section-label">// What I've built</div>  
    <h2>Projects</h2>  
    <p class="section-intro">Hands-on projects that push my skills and solve real problems.</p>  
  </div>  
  <div class="projects-grid fade-up">  
    <div class="project-card">  
      <div class="project-num">01 — Hackathon</div>  
      <div class="project-title">Bike-Themed MERN Stack App</div>  
      <p class="project-desc">  
        A full-stack web application built collaboratively during a hackathon. Focused on   
        responsive UI design, clean backend integration, and real-time data handling   
        across the full MERN stack.  
      </p>  
      <div class="project-stack">  
        <span class="tag accent">MongoDB</span>  
        <span class="tag accent">Express.js</span>  
        <span class="tag accent">React.js</span>  
        <span class="tag accent">Node.js</span>  
      </div>  
    </div>  
    <div class="project-card">  
      <div class="project-num">02 — Mobile + Web</div>  
      <div class="project-title">QR-Based Smart Attendance System</div>  
      <p class="project-desc">  
        A campus management system with QR attendance, GPS validation, and JWT-based role   
        authentication for Students, Faculty, and Admins. Includes real-time messaging   
        and push notifications via Socket.io and Firebase.  
      </p>  
      <div class="project-stack">  
        <span class="tag accent">Flutter</span>  
        <span class="tag">Firebase</span>  
        <span class="tag">Socket.io</span>  
        <span class="tag">JWT</span>  
        <span class="tag">GPS API</span>  
      </div>  
    </div>  
  </div>  
</section>  <!-- ACHIEVEMENTS -->  <section id="achievements">  
  <div class="fade-up">  
    <div class="section-label">// Recognition</div>  
    <h2>Achievements</h2>  
  </div>  
  <div class="ach-grid fade-up">  
    <div class="ach-card">  
      <div class="ach-icon">🏆</div>  
      <div>  
        <div class="ach-title">Naan Mudhalvan Hackathon Finalist</div>  
        <div class="ach-desc">  
          Reached the final round of a state-level team hackathon with the   
          bike-themed MERN stack project, competing among hundreds of teams.  
        </div>  
      </div>  
    </div>  
    <div class="ach-card">  
      <div class="ach-icon">📄</div>  
      <div>  
        <div class="ach-title">Paper Presentation — Karpagam University</div>  
        <div class="ach-desc">  
          Presented a technical paper on emerging technologies in computer science   
          at the inter-college symposium.  
        </div>  
      </div>  
    </div>  
  </div>  
</section>  <!-- CONTACT -->  <section id="contact">  
  <div class="fade-up">  
    <div class="section-label">// Let's connect</div>  
    <h2>Get In Touch</h2>  
    <p class="section-intro">  
      I'm actively looking for internship and full-time frontend / full-stack opportunities.   
      Drop me a message — I'd love to chat!  
    </p>  
  </div>  
  <div class="contact-links fade-up">  
    <a href="mailto:yaswanthkrishnan5@gmail.com" class="contact-link">  
      <span class="icon">✉️</span> yaswanthkrishnan5@gmail.com  
    </a>  
    <a href="https://linkedin.com/in/yaswanth-k-475363385" target="_blank" class="contact-link">  
      <span class="icon">💼</span> LinkedIn  
    </a>  
    <a href="https://github.com/Yaswanth1204" target="_blank" class="contact-link">  
      <span class="icon">🐙</span> GitHub  
    </a>  
    <a href="tel:+918300840928" class="contact-link">  
      <span class="icon">📞</span> +91 83008 40928  
    </a>  
  </div>  
</section>  <!-- FOOTER -->  <footer>  
  <div class="footer-copy">© 2026 Yaswanth K. All rights reserved.</div>  
  <div class="footer-mono">Designed & built with ♥</div>  
</footer>  <script>  
  // Cursor  
  const cursor = document.getElementById('cursor');  
  document.addEventListener('mousemove', e => {  
    cursor.style.left = e.clientX + 'px';  
    cursor.style.top  = e.clientY + 'px';  
  });  
  
  // Fade-up on scroll  
  const observer = new IntersectionObserver(entries => {  
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });  
  }, { threshold: 0.12 });  
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));  
</script>  </body>  
</html>
