<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>4-Month MERN Stack Roadmap</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: #1e1e2e;
    --m1: #00ff88;
    --m2: #00b4ff;
    --m3: #ff6b35;
    --m4: #a855f7;
    --text: #e2e8f0;
    --muted: #64748b;
    --card: #13131d;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 60px 24px;
    position: relative;
    background:
      radial-gradient(ellipse 80% 60% at 50% 0%, rgba(0,255,136,0.07) 0%, transparent 60%),
      radial-gradient(ellipse 50% 40% at 80% 80%, rgba(168,85,247,0.06) 0%, transparent 50%),
      var(--bg);
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,136,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,136,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
  }

  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--m1);
    border: 1px solid rgba(0,255,136,0.3);
    padding: 6px 16px;
    border-radius: 2px;
    margin-bottom: 32px;
    display: inline-block;
  }

  h1 {
    font-size: clamp(3rem, 8vw, 7rem);
    font-weight: 800;
    line-height: 0.9;
    letter-spacing: -3px;
    margin-bottom: 12px;
  }

  h1 .mern {
    display: block;
    background: linear-gradient(135deg, #00ff88, #00b4ff, #a855f7);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  h1 .stack {
    display: block;
    color: var(--text);
  }

  .subtitle {
    font-size: 1.1rem;
    color: var(--muted);
    max-width: 500px;
    margin: 24px auto 48px;
    font-weight: 400;
  }

  .overview-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
    max-width: 900px;
    width: 100%;
  }

  .ov-cell {
    background: var(--card);
    padding: 20px 24px;
    text-align: left;
    transition: background 0.2s;
  }

  .ov-cell:hover { background: #16161f; }

  .ov-num {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    margin-bottom: 8px;
  }

  .ov-title {
    font-size: 0.85rem;
    font-weight: 700;
    margin-bottom: 4px;
  }

  .ov-sub {
    font-size: 0.75rem;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
  }

  .ov-cell:nth-child(1) .ov-title { color: var(--m1); }
  .ov-cell:nth-child(2) .ov-title { color: var(--m2); }
  .ov-cell:nth-child(3) .ov-title { color: var(--m3); }
  .ov-cell:nth-child(4) .ov-title { color: var(--m4); }

  /* MAIN CONTENT */
  .container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 80px 24px;
  }

  .month-block {
    margin-bottom: 80px;
    position: relative;
  }

  .month-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 32px;
    padding-bottom: 24px;
    border-bottom: 1px solid var(--border);
  }

  .month-num {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    padding: 4px 10px;
    border-radius: 2px;
    text-transform: uppercase;
    flex-shrink: 0;
  }

  .m1-accent { background: rgba(0,255,136,0.1); color: var(--m1); border: 1px solid rgba(0,255,136,0.2); }
  .m2-accent { background: rgba(0,180,255,0.1); color: var(--m2); border: 1px solid rgba(0,180,255,0.2); }
  .m3-accent { background: rgba(255,107,53,0.1); color: var(--m3); border: 1px solid rgba(255,107,53,0.2); }
  .m4-accent { background: rgba(168,85,247,0.1); color: var(--m4); border: 1px solid rgba(168,85,247,0.2); }

  .month-title {
    font-size: 1.6rem;
    font-weight: 800;
    letter-spacing: -0.5px;
  }

  .month-tagline {
    font-family: 'Space Mono', monospace;
    font-size: 0.75rem;
    color: var(--muted);
    margin-left: auto;
    font-style: italic;
  }

  .weeks-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .week-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 24px;
    transition: border-color 0.2s, transform 0.2s;
  }

  .week-card:hover {
    transform: translateY(-2px);
  }

  .m1 .week-card:hover { border-color: rgba(0,255,136,0.3); }
  .m2 .week-card:hover { border-color: rgba(0,180,255,0.3); }
  .m3 .week-card:hover { border-color: rgba(255,107,53,0.3); }
  .m4 .week-card:hover { border-color: rgba(168,85,247,0.3); }

  .week-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    margin-bottom: 10px;
    text-transform: uppercase;
  }

  .week-title {
    font-size: 1rem;
    font-weight: 700;
    margin-bottom: 16px;
  }

  .topic-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .topic-list li {
    font-size: 0.82rem;
    color: #94a3b8;
    display: flex;
    align-items: flex-start;
    gap: 8px;
    font-family: 'Space Mono', monospace;
    line-height: 1.4;
  }

  .topic-list li::before {
    content: '▸';
    flex-shrink: 0;
    margin-top: 1px;
  }

  .m1 .topic-list li::before { color: var(--m1); }
  .m2 .topic-list li::before { color: var(--m2); }
  .m3 .topic-list li::before { color: var(--m3); }
  .m4 .topic-list li::before { color: var(--m4); }

  .project-card {
    margin-top: 20px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 20px 24px;
    display: flex;
    align-items: center;
    gap: 20px;
    grid-column: 1 / -1;
  }

  .project-icon {
    font-size: 2rem;
    flex-shrink: 0;
  }

  .project-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    margin-bottom: 4px;
  }

  .project-title {
    font-size: 1rem;
    font-weight: 700;
  }

  .project-desc {
    font-size: 0.82rem;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    margin-top: 4px;
  }

  /* MILESTONES */
  .milestones {
    margin-bottom: 80px;
  }

  .section-heading {
    font-size: 1.4rem;
    font-weight: 800;
    letter-spacing: -0.5px;
    margin-bottom: 24px;
    padding-bottom: 16px;
    border-bottom: 1px solid var(--border);
  }

  .milestone-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
  }

  .milestone-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 20px;
  }

  .milestone-month {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    margin-bottom: 10px;
    text-transform: uppercase;
  }

  .milestone-card:nth-child(1) .milestone-month { color: var(--m1); }
  .milestone-card:nth-child(2) .milestone-month { color: var(--m2); }
  .milestone-card:nth-child(3) .milestone-month { color: var(--m3); }
  .milestone-card:nth-child(4) .milestone-month { color: var(--m4); }

  .milestone-text {
    font-size: 0.82rem;
    color: #94a3b8;
    font-family: 'Space Mono', monospace;
    line-height: 1.5;
  }

  /* STACK */
  .stack-section {
    margin-bottom: 80px;
  }

  .stack-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }

  .stack-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 16px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .stack-key {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 1px;
    color: var(--muted);
    text-transform: uppercase;
  }

  .stack-val {
    font-family: 'Space Mono', monospace;
    font-size: 0.82rem;
    color: var(--m1);
    font-weight: 700;
  }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 40px 24px;
    text-align: center;
    font-family: 'Space Mono', monospace;
    font-size: 0.75rem;
    color: var(--muted);
  }

  footer span {
    color: var(--m1);
  }

  @media (max-width: 768px) {
    .overview-grid { grid-template-columns: 1fr 1fr; }
    .weeks-grid { grid-template-columns: 1fr; }
    .milestone-row { grid-template-columns: 1fr 1fr; }
    .stack-grid { grid-template-columns: 1fr 1fr; }
    .month-tagline { display: none; }
  }

  @media (max-width: 480px) {
    .overview-grid { grid-template-columns: 1fr; }
    .milestone-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <div class="badge">Developer Roadmap · 2025–2026</div>
  <h1>
    <span class="mern">MERN</span>
    <span class="stack">STACK</span>
  </h1>
  <p class="subtitle">A structured 4-month plan to go from fundamentals to full-stack developer — production-ready, job-ready.</p>

  <div class="overview-grid">
    <div class="ov-cell">
      <div class="ov-num">Month 01</div>
      <div class="ov-title">JS + Node.js</div>
      <div class="ov-sub">The Engine Room</div>
    </div>
    <div class="ov-cell">
      <div class="ov-num">Month 02</div>
      <div class="ov-title">MongoDB + Express</div>
      <div class="ov-sub">Building the Backbone</div>
    </div>
    <div class="ov-cell">
      <div class="ov-num">Month 03</div>
      <div class="ov-title">React.js</div>
      <div class="ov-sub">Bringing It to Life</div>
    </div>
    <div class="ov-cell">
      <div class="ov-num">Month 04</div>
      <div class="ov-title">Integration + Deploy</div>
      <div class="ov-sub">Ship It</div>
    </div>
  </div>
</section>

<!-- MAIN -->
<div class="container">

  <!-- MONTH 1 -->
  <div class="month-block m1">
    <div class="month-header">
      <span class="month-num m1-accent">Month 01</span>
      <h2 class="month-title">JavaScript Mastery + Node.js</h2>
      <span class="month-tagline">"The Engine Room"</span>
    </div>
    <div class="weeks-grid">
      <div class="week-card">
        <div class="week-label">Week 1–2</div>
        <div class="week-title">JavaScript Deep Dive</div>
        <ul class="topic-list">
          <li>ES6+: let/const, arrow fns, template literals</li>
          <li>Destructuring, spread/rest operators</li>
          <li>Promises, async/await, error handling</li>
          <li>Array methods: map, filter, reduce</li>
          <li>Closures, scope, hoisting, this keyword</li>
          <li>Modules: ESM vs CommonJS</li>
          <li>Event loop, call stack, microtasks</li>
          <li>OOP: Classes, inheritance, prototypes</li>
        </ul>
      </div>
      <div class="week-card">
        <div class="week-label">Week 3–4</div>
        <div class="week-title">Node.js Foundations</div>
        <ul class="topic-list">
          <li>Node.js runtime, V8, libuv</li>
          <li>Core modules: fs, path, os, events, http</li>
          <li>npm: package.json, scripts, versioning</li>
          <li>Build a HTTP server from scratch</li>
          <li>nodemon, dotenv, environment vars</li>
          <li>File system read/write/delete ops</li>
          <li>Streams and Buffers (basics)</li>
          <li>Error handling patterns</li>
        </ul>
      </div>
      <div class="project-card" style="grid-column: 1 / -1;">
        <div class="project-icon">🛠️</div>
        <div>
          <div class="project-label">Month 1 Project</div>
          <div class="project-title">CLI Todo App</div>
          <div class="project-desc">Node.js + file system persistence · CRUD via terminal commands</div>
        </div>
      </div>
    </div>
  </div>

  <!-- MONTH 2 -->
  <div class="month-block m2">
    <div class="month-header">
      <span class="month-num m2-accent">Month 02</span>
      <h2 class="month-title">MongoDB + Express.js APIs</h2>
      <span class="month-tagline">"Building the Backbone"</span>
    </div>
    <div class="weeks-grid">
      <div class="week-card">
        <div class="week-label">Week 5–6</div>
        <div class="week-title">MongoDB + Mongoose</div>
        <ul class="topic-list">
          <li>NoSQL document model vs relational</li>
          <li>MongoDB Atlas setup + Compass</li>
          <li>CRUD operations via shell</li>
          <li>Mongoose: Schema, Model, validation</li>
          <li>Relationships: referencing vs embedding</li>
          <li>Queries: find, findById, deleteOne</li>
          <li>Indexing basics for performance</li>
          <li>Aggregation pipeline ($match, $group)</li>
        </ul>
      </div>
      <div class="week-card">
        <div class="week-label">Week 7–8</div>
        <div class="week-title">Express.js REST APIs</div>
        <ul class="topic-list">
          <li>Middleware concept + Express basics</li>
          <li>Routes: GET, POST, PUT, PATCH, DELETE</li>
          <li>express.Router() modular routing</li>
          <li>MVC: Models / Controllers / Routes</li>
          <li>JWT authentication + bcrypt hashing</li>
          <li>Protected routes with middleware</li>
          <li>Input validation (Joi / express-validator)</li>
          <li>Error handling middleware + CORS</li>
        </ul>
      </div>
      <div class="project-card" style="grid-column: 1 / -1;">
        <div class="project-icon">🔌</div>
        <div>
          <div class="project-label">Month 2 Project</div>
          <div class="project-title">Blog REST API</div>
          <div class="project-desc">User auth · JWT-protected CRUD posts · MongoDB Atlas · Postman tested</div>
        </div>
      </div>
    </div>
  </div>

  <!-- MONTH 3 -->
  <div class="month-block m3">
    <div class="month-header">
      <span class="month-num m3-accent">Month 03</span>
      <h2 class="month-title">React.js Frontend</h2>
      <span class="month-tagline">"Bringing It to Life"</span>
    </div>
    <div class="weeks-grid">
      <div class="week-card">
        <div class="week-label">Week 9–10</div>
        <div class="week-title">React Core</div>
        <ul class="topic-list">
          <li>Virtual DOM, component model, JSX</li>
          <li>Props, PropTypes, state (useState)</li>
          <li>Event handling, conditional rendering</li>
          <li>Lists, keys, controlled forms</li>
          <li>useEffect — lifecycle management</li>
          <li>Fetching data with axios/fetch</li>
          <li>Component composition patterns</li>
          <li>Vite setup + project structure</li>
        </ul>
      </div>
      <div class="week-card">
        <div class="week-label">Week 11–12</div>
        <div class="week-title">React Advanced</div>
        <ul class="topic-list">
          <li>useContext, useRef, useMemo, useCallback</li>
          <li>Custom hooks</li>
          <li>React Router v6: Routes, useNavigate</li>
          <li>Protected frontend routes</li>
          <li>State: Context API → Zustand intro</li>
          <li>Tailwind CSS + component libraries</li>
          <li>TanStack Query for server state</li>
          <li>Error boundaries</li>
        </ul>
      </div>
      <div class="project-card" style="grid-column: 1 / -1;">
        <div class="project-icon">⚛️</div>
        <div>
          <div class="project-label">Month 3 Project</div>
          <div class="project-title">Blog Frontend</div>
          <div class="project-desc">Connects to Month 2 API · Auth state · Full CRUD UI · React Router navigation</div>
        </div>
      </div>
    </div>
  </div>

  <!-- MONTH 4 -->
  <div class="month-block m4">
    <div class="month-header">
      <span class="month-num m4-accent">Month 04</span>
      <h2 class="month-title">Integration + Deployment</h2>
      <span class="month-tagline">"Ship It"</span>
    </div>
    <div class="weeks-grid">
      <div class="week-card">
        <div class="week-label">Week 13–14</div>
        <div class="week-title">Full-Stack + DevOps</div>
        <ul class="topic-list">
          <li>Connect React ↔ Express (CORS, proxy)</li>
          <li>Axios interceptors for auth tokens</li>
          <li>File uploads with multer</li>
          <li>Pagination + search APIs</li>
          <li>Real-time intro with Socket.io</li>
          <li>Deploy backend → Render / Railway</li>
          <li>Deploy frontend → Vercel / Netlify</li>
          <li>MongoDB Atlas production + env vars</li>
        </ul>
      </div>
      <div class="week-card">
        <div class="week-label">Week 15–16</div>
        <div class="week-title">Capstone Projects</div>
        <ul class="topic-list">
          <li>E-Commerce: products, cart, checkout</li>
          <li>Admin panel: add/edit/delete products</li>
          <li>Stripe payment integration</li>
          <li>Solo project of your choice</li>
          <li>Write professional READMEs</li>
          <li>GitHub portfolio setup</li>
          <li>LinkedIn + resume update</li>
          <li>Mock interview prep</li>
        </ul>
      </div>
      <div class="project-card" style="grid-column: 1 / -1;">
        <div class="project-icon">🚀</div>
        <div>
          <div class="project-label">Month 4 Projects</div>
          <div class="project-title">E-Commerce Store + Solo Full-Stack App</div>
          <div class="project-desc">Both deployed publicly · Stripe integrated · Portfolio-ready with READMEs</div>
        </div>
      </div>
    </div>
  </div>

  <!-- MILESTONES -->
  <div class="milestones">
    <h2 class="section-heading">Month-End Milestones</h2>
    <div class="milestone-row">
      <div class="milestone-card">
        <div class="milestone-month">End of Month 1</div>
        <div class="milestone-text">Write advanced JS, build CLI tools, understand Node.js internals and async patterns</div>
      </div>
      <div class="milestone-card">
        <div class="milestone-month">End of Month 2</div>
        <div class="milestone-text">Build and test a secure REST API with JWT auth, MongoDB, and proper MVC structure</div>
      </div>
      <div class="milestone-card">
        <div class="milestone-month">End of Month 3</div>
        <div class="milestone-text">Build a multi-page React SPA consuming a real API with auth and state management</div>
      </div>
      <div class="milestone-card">
        <div class="milestone-month">End of Month 4</div>
        <div class="milestone-text">Deploy a complete MERN app, explain your code confidently in technical interviews</div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="stack-section">
    <h2 class="section-heading">Tech Stack</h2>
    <div class="stack-grid">
      <div class="stack-item"><span class="stack-key">Runtime</span><span class="stack-val">Node.js v20+</span></div>
      <div class="stack-item"><span class="stack-key">Package Manager</span><span class="stack-val">npm / pnpm</span></div>
      <div class="stack-item"><span class="stack-key">Backend</span><span class="stack-val">Express.js</span></div>
      <div class="stack-item"><span class="stack-key">Database</span><span class="stack-val">MongoDB + Mongoose</span></div>
      <div class="stack-item"><span class="stack-key">Frontend</span><span class="stack-val">React 18 + Vite</span></div>
      <div class="stack-item"><span class="stack-key">Styling</span><span class="stack-val">Tailwind CSS</span></div>
      <div class="stack-item"><span class="stack-key">Auth</span><span class="stack-val">JWT + bcrypt</span></div>
      <div class="stack-item"><span class="stack-key">Deploy: Backend</span><span class="stack-val">Render / Railway</span></div>
      <div class="stack-item"><span class="stack-key">Deploy: Frontend</span><span class="stack-val">Vercel / Netlify</span></div>
      <div class="stack-item"><span class="stack-key">DB Cloud</span><span class="stack-val">MongoDB Atlas</span></div>
      <div class="stack-item"><span class="stack-key">Version Control</span><span class="stack-val">Git + GitHub</span></div>
      <div class="stack-item"><span class="stack-key">API Testing</span><span class="stack-val">Thunder Client</span></div>
    </div>
  </div>

</div>

<footer>
  <p>4 MONTHS · 16 WEEKS · <span>MERN STACK</span> · BUILT WITH PURPOSE</p>
  <p style="margin-top: 8px; font-size: 0.65rem;">Commit to the roadmap. Ship something every week. The rest takes care of itself.</p>
</footer>

</body>
</html>
