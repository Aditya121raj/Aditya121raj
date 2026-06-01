<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aditya Raj — Full-Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --accent: #1D9E75;
    --accent-light: #E1F5EE;
    --accent-dark: #085041;
    --bg: #ffffff;
    --bg2: #f7f7f5;
    --bg3: #f1efe8;
    --t1: #1a1a18;
    --t2: #5f5e5a;
    --t3: #888780;
    --b: rgba(0,0,0,0.1);
    --b2: rgba(0,0,0,0.2);
    --radius-md: 8px;
    --radius-lg: 12px;
  }
  body { font-family: 'Outfit', sans-serif; color: var(--t1); background: #fafaf8; min-height: 100vh; }
  .page { max-width: 760px; margin: 0 auto; padding: 3rem 2rem 5rem; }

  .hero { padding: 2.5rem 0 2rem; border-bottom: 0.5px solid var(--b); }
  .hero-tag { font-family: 'DM Mono', monospace; font-size: 11px; letter-spacing: 0.12em; text-transform: uppercase; color: var(--accent); margin-bottom: 0.75rem; }
  .hero-name { font-family: 'DM Serif Display', serif; font-size: 52px; line-height: 1.05; color: var(--t1); margin-bottom: 0.5rem; }
  .hero-name em { font-style: italic; color: var(--accent); }
  .hero-title { font-size: 15px; color: var(--t2); font-weight: 300; margin-bottom: 1.25rem; }
  .hero-links { display: flex; gap: 10px; flex-wrap: wrap; }
  .pill { display: inline-flex; align-items: center; gap: 5px; padding: 5px 12px; border: 0.5px solid var(--b2); border-radius: 20px; font-size: 12px; font-family: 'DM Mono', monospace; color: var(--t2); text-decoration: none; transition: all 0.15s; }
  .pill:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-light); }
  .pill i { font-size: 13px; }

  .stats-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin: 1.75rem 0; }
  .stat { background: var(--bg2); border-radius: var(--radius-md); padding: 1rem; text-align: center; }
  .stat-n { font-family: 'DM Serif Display', serif; font-size: 28px; color: var(--accent); display: block; }
  .stat-l { font-size: 11px; color: var(--t2); font-family: 'DM Mono', monospace; letter-spacing: 0.05em; text-transform: uppercase; margin-top: 2px; display: block; }

  section { padding: 1.75rem 0; border-bottom: 0.5px solid var(--b); }
  section:last-child { border-bottom: none; }
  .sec-hd { display: flex; align-items: center; gap: 8px; margin-bottom: 1.25rem; }
  .sec-hd-label { font-family: 'DM Mono', monospace; font-size: 11px; text-transform: uppercase; letter-spacing: 0.12em; color: var(--t3); }
  .sec-hd-line { flex: 1; height: 0.5px; background: var(--b); }

  .exp-card { background: var(--bg); border: 0.5px solid var(--b); border-radius: var(--radius-lg); padding: 1.25rem; margin-bottom: 10px; border-left: 2.5px solid var(--accent); }
  .exp-top { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 6px; flex-wrap: wrap; gap: 6px; }
  .exp-role { font-size: 15px; font-weight: 500; }
  .exp-co { font-size: 13px; color: var(--accent); font-family: 'DM Mono', monospace; }
  .exp-date { font-size: 11px; color: var(--t3); font-family: 'DM Mono', monospace; background: var(--bg2); padding: 3px 8px; border-radius: 10px; white-space: nowrap; }
  .exp-tags { display: flex; flex-wrap: wrap; gap: 5px; margin: 8px 0; }
  .tag { font-size: 11px; font-family: 'DM Mono', monospace; padding: 2px 8px; border-radius: 4px; background: var(--accent-light); color: var(--accent-dark); }
  .exp-bullets { list-style: none; margin-top: 8px; }
  .exp-bullets li { font-size: 13px; color: var(--t2); padding: 3px 0 3px 14px; position: relative; line-height: 1.5; }
  .exp-bullets li::before { content: '→'; position: absolute; left: 0; color: var(--accent); font-size: 11px; top: 5px; }

  .proj-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
  .proj-card { background: var(--bg); border: 0.5px solid var(--b); border-radius: var(--radius-lg); padding: 1.25rem; display: flex; flex-direction: column; gap: 8px; transition: border-color 0.15s; }
  .proj-card:hover { border-color: var(--accent); }
  .proj-icon { width: 36px; height: 36px; border-radius: 8px; background: var(--accent-light); display: flex; align-items: center; justify-content: center; }
  .proj-icon i { font-size: 18px; color: var(--accent); }
  .proj-name { font-size: 14px; font-weight: 500; }
  .proj-desc { font-size: 12px; color: var(--t2); line-height: 1.5; flex: 1; }
  .proj-foot { display: flex; justify-content: space-between; align-items: center; margin-top: 4px; }
  .proj-stat { font-size: 11px; font-family: 'DM Mono', monospace; color: var(--accent); }

  .skills-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .skill-group { background: var(--bg2); border-radius: var(--radius-md); padding: 1rem; }
  .skill-group-name { font-size: 11px; font-family: 'DM Mono', monospace; text-transform: uppercase; letter-spacing: 0.1em; color: var(--t3); margin-bottom: 8px; }
  .skill-chips { display: flex; flex-wrap: wrap; gap: 5px; }
  .chip { font-size: 11px; padding: 3px 8px; border-radius: 4px; background: var(--bg); border: 0.5px solid var(--b); color: var(--t2); font-family: 'DM Mono', monospace; }

  .ach-row { display: flex; gap: 10px; flex-wrap: wrap; margin-top: 4px; }
  .ach-card { background: var(--bg2); border-radius: var(--radius-md); padding: 0.75rem 1rem; flex: 1; min-width: 140px; display: flex; align-items: center; gap: 10px; }
  .ach-icon { font-size: 20px; color: var(--accent); }
  .ach-text { font-size: 12px; color: var(--t2); line-height: 1.4; }
  .ach-text strong { display: block; font-size: 13px; color: var(--t1); font-weight: 500; margin-bottom: 2px; }

  .edu-row { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 6px; }
  .edu-deg { font-size: 15px; font-weight: 500; }
  .edu-uni { font-size: 13px; color: var(--t2); margin-top: 3px; }
  .edu-cw { margin-top: 8px; font-size: 12px; color: var(--t3); font-family: 'DM Mono', monospace; line-height: 1.6; }

  @media (max-width: 600px) {
    .hero-name { font-size: 36px; }
    .stats-row { grid-template-columns: 1fr 1fr; }
    .proj-grid { grid-template-columns: 1fr; }
    .skills-grid { grid-template-columns: 1fr; }
    .ach-row { flex-direction: column; }
  }
</style>
</head>
<body>
<div class="page">

  <div class="hero">
    <div class="hero-tag">Full-Stack Developer</div>
    <div class="hero-name">Aditya <em>Raj</em></div>
    <div class="hero-title">AI-powered & real-time systems · React · Next.js · Node.js · Delhi, India</div>
    <div class="hero-links">
      <a class="pill" href="mailto:adiraj1706@gmail.com"><i class="ti ti-mail"></i>adiraj1706@gmail.com</a>
      <a class="pill" href="https://github.com/Aditya121raj" target="_blank"><i class="ti ti-brand-github"></i>GitHub</a>
      <a class="pill" href="https://linkedin.com" target="_blank"><i class="ti ti-brand-linkedin"></i>LinkedIn</a>
      <a class="pill" href="https://leetcode.com" target="_blank"><i class="ti ti-code"></i>LeetCode</a>
      <a class="pill" href="#"><i class="ti ti-world"></i>Portfolio</a>
    </div>
    <div class="stats-row">
      <div class="stat"><span class="stat-n">27K+</span><span class="stat-l">Users Served</span></div>
      <div class="stat"><span class="stat-n">799K+</span><span class="stat-l">Monthly Views</span></div>
      <div class="stat"><span class="stat-n">300+</span><span class="stat-l">LeetCode Solved</span></div>
    </div>
  </div>

  <section>
    <div class="sec-hd"><span class="sec-hd-label">Experience</span><div class="sec-hd-line"></div></div>
    <div class="exp-card">
      <div class="exp-top">
        <div>
          <div class="exp-role">Frontend Developer Intern</div>
          <div class="exp-co">Talentd.in</div>
        </div>
        <div class="exp-date">Sep 2025 – Mar 2026 · Remote</div>
      </div>
      <div class="exp-tags">
        <span class="tag">Next.js</span><span class="tag">React Native</span><span class="tag">TailwindCSS</span><span class="tag">REST APIs</span><span class="tag">WebSockets</span><span class="tag">Agile/Scrum</span>
      </div>
      <ul class="exp-bullets">
        <li>Shipped production UI features to 27,000+ users with ~15% reduction in post-release issue reports</li>
        <li>Engineered reusable React/Next.js components, integrated 10+ REST APIs with structured error handling</li>
        <li>Collaborated in Agile/Scrum with code reviews, feature-based development, and unit testing practices</li>
      </ul>
    </div>
  </section>

  <section>
    <div class="sec-hd"><span class="sec-hd-label">Projects</span><div class="sec-hd-line"></div></div>
    <div class="proj-grid">
      <div class="proj-card">
        <div class="proj-icon"><i class="ti ti-robot"></i></div>
        <div class="proj-name">ResumeIQ</div>
        <div class="proj-desc">AI resume classifier using TF-IDF, KNN, and OpenAI API for personalized career insights across 25 job categories</div>
        <div class="exp-tags" style="margin:0"><span class="tag">Python</span><span class="tag">scikit-learn</span><span class="tag">OpenAI</span></div>
        <div class="proj-foot">
          <span class="proj-stat">98.44% accuracy · 1K+ resumes</span>
          <a href="https://github.com/Aditya121raj/resumeiq" target="_blank" style="color:var(--t3);font-size:13px;"><i class="ti ti-external-link"></i></a>
        </div>
      </div>
      <div class="proj-card">
        <div class="proj-icon"><i class="ti ti-books"></i></div>
        <div class="proj-name">BookHaven</div>
        <div class="proj-desc">Full-stack MERN bookstore with 15+ REST endpoints, JWT auth, RBAC, and fully responsive TailwindCSS UI</div>
        <div class="exp-tags" style="margin:0"><span class="tag">React</span><span class="tag">Node.js</span><span class="tag">MongoDB</span></div>
        <div class="proj-foot">
          <span class="proj-stat">Deployed on Vercel + Render</span>
          <a href="https://github.com/Aditya121raj/bookhaven" target="_blank" style="color:var(--t3);font-size:13px;"><i class="ti ti-external-link"></i></a>
        </div>
      </div>
      <div class="proj-card">
        <div class="proj-icon"><i class="ti ti-messages"></i></div>
        <div class="proj-name">QuickChat</div>
        <div class="proj-desc">AI-powered real-time chat with OpenAI embedded inline via WebSockets — no context switch needed</div>
        <div class="exp-tags" style="margin:0"><span class="tag">WebSockets</span><span class="tag">OpenAI API</span><span class="tag">JWT</span></div>
        <div class="proj-foot">
          <span class="proj-stat">Multi-user · MongoDB sessions</span>
          <a href="https://github.com/Aditya121raj/quickchat" target="_blank" style="color:var(--t3);font-size:13px;"><i class="ti ti-external-link"></i></a>
        </div>
      </div>
    </div>
  </section>

  <section>
    <div class="sec-hd"><span class="sec-hd-label">Skills</span><div class="sec-hd-line"></div></div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-name">Frontend</div>
        <div class="skill-chips"><span class="chip">React.js</span><span class="chip">Next.js</span><span class="chip">React Native</span><span class="chip">TailwindCSS</span><span class="chip">Redux</span><span class="chip">ShadCN UI</span></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-name">Backend</div>
        <div class="skill-chips"><span class="chip">Node.js</span><span class="chip">Express.js</span><span class="chip">WebSockets</span><span class="chip">JWT Auth</span><span class="chip">REST API</span></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-name">Database & AI</div>
        <div class="skill-chips"><span class="chip">MongoDB</span><span class="chip">PostgreSQL</span><span class="chip">Redis</span><span class="chip">OpenAI API</span><span class="chip">scikit-learn</span></div>
      </div>
      <div class="skill-group">
        <div class="skill-group-name">Languages & Tools</div>
        <div class="skill-chips"><span class="chip">JavaScript</span><span class="chip">TypeScript</span><span class="chip">Python</span><span class="chip">Docker</span><span class="chip">Git</span><span class="chip">CI/CD</span></div>
      </div>
    </div>
  </section>

  <section>
    <div class="sec-hd"><span class="sec-hd-label">Education</span><div class="sec-hd-line"></div></div>
    <div class="exp-card">
      <div class="edu-row">
        <div>
          <div class="edu-deg">B.Tech — Computer Science & Engineering</div>
          <div class="edu-uni">Galgotias University, Greater Noida</div>
        </div>
        <div class="exp-date">2021 – 2025</div>
      </div>
      <div class="edu-cw">DSA · DBMS · Operating Systems · Computer Networks · Machine Learning · System Design</div>
    </div>
  </section>

  <section>
    <div class="sec-hd"><span class="sec-hd-label">Achievements</span><div class="sec-hd-line"></div></div>
    <div class="ach-row">
      <div class="ach-card"><i class="ti ti-trophy ach-icon"></i><div class="ach-text"><strong>LeetCode Top 15%</strong>300+ problems solved globally</div></div>
      <div class="ach-card"><i class="ti ti-star ach-icon"></i><div class="ach-text"><strong>HackerRank 5★ Gold</strong>Problem solving certified</div></div>
      <div class="ach-card"><i class="ti ti-rocket ach-icon"></i><div class="ach-text"><strong>NASA Space Apps 2022</strong>Selected for global hackathon</div></div>
      <div class="ach-card"><i class="ti ti-award ach-icon"></i><div class="ach-text"><strong>Smart India Hackathon</strong>Advanced to college finals</div></div>
    </div>
  </section>

</div>
</body>
</html>
