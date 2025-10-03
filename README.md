<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Interactive Digital Portfolio — Your Name</title>
  <meta name="description" content="Interactive portfolio with projects, skills, timeline and contact form" />
  <style>
    /* ---------- Basic Reset ---------- */
    *,*::before,*::after{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter, ui-sans-serif, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;line-height:1.4;color:#0f172a;background:linear-gradient(180deg,#f8fafc 0%, #ffffff 100%)}:root{
  --accent:#0ea5a3; /* teal */
  --muted:#64748b;
  --card:#ffffff;
  --glass: rgba(255,255,255,0.6);
  --radius:14px;
  --shadow: 0 6px 20px rgba(2,6,23,0.08);
  --max-width:1100px;
}

/* ---------- Layout ---------- */
.container{max-width:var(--max-width);margin:36px auto;padding:24px}
header{display:flex;align-items:center;justify-content:space-between;gap:12px}
.brand{display:flex;align-items:center;gap:12px}
.logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#60a5fa);display:grid;place-items:center;color:white;font-weight:700}
nav{display:flex;gap:8px;align-items:center}
nav a{color:var(--muted);text-decoration:none;padding:8px 10px;border-radius:8px;font-weight:600}
nav a:hover{color:var(--accent);background:rgba(14,165,163,0.06)}
.cta{background:var(--accent);color:white;padding:10px 14px;border-radius:10px;text-decoration:none;font-weight:700}

/* ---------- Hero ---------- */
.hero{display:grid;grid-template-columns:1fr 360px;gap:28px;align-items:center;margin-top:28px}
.intro{background:var(--card);border-radius:var(--radius);padding:28px;box-shadow:var(--shadow)}
.intro h1{margin:0;font-size:clamp(22px,3vw,34px)}
.intro p{color:var(--muted);margin-top:10px}
.skills-row{display:flex;flex-wrap:wrap;gap:8px;margin-top:14px}
.skill-pill{background:var(--glass);padding:8px 10px;border-radius:999px;font-weight:600;color:#053;backdrop-filter:blur(6px)}

.profile-card{background:linear-gradient(180deg,#fff 0,#f8fafc 100%);border-radius:18px;padding:20px;box-shadow:var(--shadow);text-align:center}
.avatar{width:160px;height:160px;border-radius:18px;display:inline-block;overflow:hidden;margin:6px auto;border:6px solid white}
.avatar img{width:100%;height:100%;object-fit:cover;display:block}
.profile-card h3{margin:10px 0 6px}
.meta{color:var(--muted);font-size:14px}

/* ---------- Projects & Filters ---------- */
section{margin-top:28px}
.section-title{display:flex;align-items:center;justify-content:space-between}
.filters{display:flex;gap:8px;margin-top:12px}
.filter-btn{padding:8px 12px;border-radius:999px;border:1px solid rgba(10,10,10,0.04);background:transparent;cursor:pointer;font-weight:700}
.filter-btn.active{background:var(--accent);color:white;border-color:transparent}

.projects-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-top:16px}
.card{background:var(--card);padding:14px;border-radius:12px;box-shadow:var(--shadow);cursor:pointer;transition:transform .18s ease,box-shadow .18s ease}
.card:hover{transform:translateY(-6px);box-shadow:0 18px 40px rgba(2,6,23,0.12)}
.card .tags{display:flex;gap:8px;flex-wrap:wrap;margin-top:10px}
.tag{font-size:12px;padding:6px 8px;border-radius:999px;background:rgba(2,6,23,0.04);font-weight:700}

/* ---------- Modal ---------- */
.modal{position:fixed;inset:0;display:grid;place-items:center;background:rgba(2,6,23,0.48);opacity:0;pointer-events:none;transition:opacity .18s ease}
.modal.open{opacity:1;pointer-events:auto}
.modal-panel{width:min(880px,94%);background:var(--card);border-radius:14px;padding:20px;box-shadow:0 30px 70px rgba(2,6,23,0.4)}
.modal-grid{display:grid;grid-template-columns:1fr 320px;gap:18px}
.modal img{width:100%;height:220px;object-fit:cover;border-radius:10px}

/* ---------- Timeline ---------- */
.timeline{margin-top:18px;border-left:3px solid rgba(14,165,163,0.12);padding-left:16px}
.timeline-item{position:relative;padding:12px 0}
.timeline-item::before{content:'';position:absolute;left:-10px;top:18px;width:14px;height:14px;border-radius:50%;background:var(--accent);border:3px solid white}

/* ---------- Contact ---------- */
.contact-card{display:grid;grid-template-columns:1fr 360px;gap:18px;background:var(--card);border-radius:12px;padding:18px;box-shadow:var(--shadow);margin-top:18px}
.form-row{display:flex;gap:8px}
input,textarea{width:100%;padding:10px;border-radius:10px;border:1px solid rgba(2,6,23,0.06);font-size:14px}
textarea{min-height:110px;resize:vertical}
.btn{background:var(--accent);color:white;padding:10px 14px;border-radius:10px;border:none;cursor:pointer;font-weight:700}

/* ---------- Footer ---------- */
footer{margin-top:26px;text-align:center;color:var(--muted);font-size:13px}

/* ---------- Responsive ---------- */
@media (max-width:980px){
  .hero{grid-template-columns:1fr}
  .projects-grid{grid-template-columns:repeat(2,1fr)}
  .modal-grid{grid-template-columns:1fr}
  .contact-card{grid-template-columns:1fr}
}
@media (max-width:600px){
  nav{display:none}
  .logo{width:48px;height:48px}
  .projects-grid{grid-template-columns:1fr}
}

/* ---------- Small accessibility helpers ---------- */
.sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}

  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">NR</div>
        <div>
          <div style="font-weight:800">Naru Rajasekhar</div>
          <div style="color:var(--muted);font-size:13px">Front-end Developer • UI / UX • Data Enthusiast</div>
        </div>
      </div><nav aria-label="Primary">
    <a href="#projects">Projects</a>
    <a href="#skills">Skills</a>
    <a href="#about">About</a>
    <a class="cta" href="#contact">Contact</a>
  </nav>
</header>

<main>
  <section class="hero" aria-labelledby="intro">
    <div class="intro" id="intro">
      <h1>Hello — I'm Naru. I build delightful web experiences.</h1>
      <p>I design and develop interactive, responsive front-ends with a focus on accessibility, performance, and maintainable code. Below are a few projects, skills and ways to contact me.</p>

      <div class="skills-row" id="skills">
        <div class="skill-pill">HTML</div>
        <div class="skill-pill">CSS</div>
        <div class="skill-pill">JavaScript</div>
        <div class="skill-pill">React</div>
        <div class="skill-pill">Figma</div>
      </div>

      <div style="margin-top:16px;display:flex;gap:10px;align-items:center">
        <a class="cta" href="#projects">View Projects</a>
        <a style="padding:10px 14px;border-radius:10px;border:1px solid rgba(2,6,23,0.06);text-decoration:none;color:var(--muted);font-weight:700" href="#about">Download CV</a>
      </div>
    </div>

    <aside class="profile-card" aria-labelledby="profile-name">
      <div class="avatar" role="img" aria-label="Profile picture">
        <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="Profile avatar placeholder">
      </div>
      <h3 id="profile-name">Naru Rajasekhar</h3>
      <div class="meta">Front-end Developer — Chennai, India</div>
      <div style="margin-top:12px;display:flex;justify-content:center;gap:8px">
        <a href="#" aria-label="github" title="GitHub">GitHub</a>
        <a href="#" aria-label="linkedin" title="LinkedIn">LinkedIn</a>
      </div>
    </aside>
  </section>

  <section id="projects" aria-labelledby="projects-title">
    <div class="section-title">
      <h2 id="projects-title">Selected Projects</h2>
      <div style="color:var(--muted)">Click a card to open details</div>
    </div>

    <div class="filters" role="tablist" aria-label="Project filters">
      <button class="filter-btn active" data-filter="all">All</button>
      <button class="filter-btn" data-filter="web">Web</button>
      <button class="filter-btn" data-filter="ui">UI</button>
      <button class="filter-btn" data-filter="data">Data</button>
    </div>

    <div class="projects-grid" id="projects-grid">
      <!-- Project card template -->
      <article class="card" data-type="web" tabindex="0" data-title="Recipe Finder" data-desc="A responsive recipe search app with filters and saved favorites." data-images="https://images.unsplash.com/photo-1512058564366-c9e3d5c6b0c0?q=80&w=1200&auto=format&fit=crop">
        <h3>Recipe Finder</h3>
        <p class="muted">Search, filter and save recipes.</p>
        <div class="tags"><span class="tag">React</span><span class="tag">APIs</span></div>
      </article>

      <article class="card" data-type="ui" tabindex="0" data-title="Mobile Banking UI" data-desc="Design and prototype of a modern mobile banking experience." data-images="https://images.unsplash.com/photo-1526378724565-8d0b2b6a1f0a?q=80&w=1200&auto=format&fit=crop">
        <h3>Mobile Banking UI</h3>
        <p class="muted">Prototype for mobile transactions UX.</p>
        <div class="tags"><span class="tag">Figma</span><span class="tag">UX</span></div>
      </article>

      <article class="card" data-type="data" tabindex="0" data-title="Bike Rental Forecast" data-desc="Time-series model predicting bike rentals for a smart city pilot." data-images="https://images.unsplash.com/photo-1520975912757-2f0b3f0b9d82?q=80&w=1200&auto=format&fit=crop">
        <h3>Bike Rental Forecast</h3>
        <p class="muted">Forecasting model + interactive dashboard.</p>
        <div class="tags"><span class="tag">Python</span><span class="tag">Dash</span></div>
      </article>

      <article class="card" data-type="web" tabindex="0" data-title="Portfolio Generator" data-desc="A tiny tool that builds a portfolio site from markdown and images." data-images="https://images.unsplash.com/photo-1503387762-592deb58ef4e?q=80&w=1200&auto=format&fit=crop">
        <h3>Portfolio Generator</h3>
        <p class="muted">CLI + static site generator.</p>
        <div class="tags"><span class="tag">Node</span><span class="tag">SSG</span></div>
      </article>

      <article class="card" data-type="ui" tabindex="0" data-title="E-commerce Redesign" data-desc="UX overhaul for a small e-commerce brand; improved conversion flows." data-images="https://images.unsplash.com/photo-1519744792095-2f2205e87b6f?q=80&w=1200&auto=format&fit=crop">
        <h3>E-commerce Redesign</h3>
        <p class="muted">A/B tested checkout improvements.</p>
        <div class="tags"><span class="tag">UX</span><span class="tag">A/B</span></div>
      </article>

      <article class="card" data-type="data" tabindex="0" data-title="Churn Classifier" data-desc="Customer churn classifier with model interpretability dashboard." data-images="https://images.unsplash.com/photo-1526378724565-8d0b2b6a1f0a?q=80&w=1200&auto=format&fit=crop">
        <h3>Churn Classifier</h3>
        <p class="muted">Explainable ML for subscription churn.</p>
        <div class="tags"><span class="tag">ML</span><span class="tag">Explainable AI</span></div>
      </article>
    </div>
  </section>

  <section id="about">
    <div class="section-title">
      <h2>About & Timeline</h2>
      <div style="color:var(--muted)">Quick background</div>
    </div>

    <p style="color:var(--muted);margin-top:12px">I’m a developer focused on building polished front-ends and data-driven tools. I enjoy turning complex problems into simple, usable interfaces.</p>

    <div class="timeline" aria-label="timeline">
      <div class="timeline-item">
        <strong>2024 — Internship at WebLabs</strong>
        <div class="muted">Worked on responsive UI and accessibility improvements.</div>
      </div>
      <div class="timeline-item">
        <strong>2025 — Bootcamp: Software & Network Security</strong>
        <div class="muted">Completed a practical bootcamp on web security fundamentals.</div>
      </div>
    </div>
  </section>

  <section id="contact">
    <div class="section-title">
      <h2>Contact</h2>
      <div style="color:var(--muted)">Say hi — I’m open to collaborations</div>
    </div>

    <div class="contact-card">
      <form id="contact-form" onsubmit="return false;" aria-label="Contact form">
        <div class="form-row">
          <input type="text" id="name" placeholder="Your name" required />
          <input type="email" id="email" placeholder="Your email" required />
        </div>
        <div style="margin-top:10px">
          <input type="text" id="subject" placeholder="Subject" />
        </div>
        <div style="margin-top:10px">
          <textarea id="message" placeholder="Message" required></textarea>
        </div>
        <div style="margin-top:10px;display:flex;gap:8px;align-items:center">
          <button class="btn" id="send-btn">Send message</button>
          <div id="form-feedback" style="color:var(--muted);font-weight:700"></div>
        </div>
      </form>

      <aside style="padding:12px">
        <h3>Get in touch</h3>
        <p style="color:var(--muted)">Email: <a href="mailto:youremail@example.com">youremail@example.com</a></p>
        <p style="color:var(--muted)">Location: Chennai, India</p>
        <div style="margin-top:12px">
          <strong>Available for:</strong>
          <ul style="color:var(--muted)">
            <li>Freelance & Contract</li>
            <li>Full-time roles</li>
            <li>Short-term collaborations</li>
          </ul>
        </div>
      </aside>
    </div>
  </section>

  <footer>
    © <span id="year"></span> Naru Rajasekhar • Built with HTML, CSS & vanilla JS
  </footer>
</main>

  </div>  <!-- Modal element -->  <div class="modal" id="project-modal" role="dialog" aria-hidden="true" aria-labelledby="modal-title">
    <div class="modal-panel" role="document">
      <div style="display:flex;align-items:center;justify-content:space-between">
        <h3 id="modal-title">Project</h3>
        <button aria-label="Close modal" id="close-modal">Close</button>
      </div>
      <div class="modal-grid" style="margin-top:12px">
        <div>
          <img id="modal-image" src="" alt="Project image">
          <h4 id="modal-subtitle" style="margin-top:10px"></h4>
          <p id="modal-desc" style="color:var(--muted)"></p>
          <div style="margin-top:12px">
            <a id="modal-link" class="btn" href="#">View live</a>
          </div>
        </div>
        <div>
          <h4>Tech & Highlights</h4>
          <ul id="modal-tech" style="color:var(--muted)"></ul>
        </div>
      </div>
    </div>
  </div>  <script>
    // small helpers & interactivity
    document.getElementById('year').textContent = new Date().getFullYear();

    // Filtering projects
    const filterBtns = document.querySelectorAll('.filter-btn');
    const cards = document.querySelectorAll('.card');
    filterBtns.forEach(btn => btn.addEventListener('click', () => {
      filterBtns.forEach(b=>b.classList.remove('active'));
      btn.classList.add('active');
      const f = btn.dataset.filter;
      cards.forEach(c => {
        c.style.display = (f === 'all' || c.dataset.type === f) ? '' : 'none';
      });
    }));

    // Modal open
    const modal = document.getElementById('project-modal');
    const modalTitle = document.getElementById('modal-title');
    const modalDesc = document.getElementById('modal-desc');
    const modalImage = document.getElementById('modal-image');
    const modalTech = document.getElementById('modal-tech');
    const modalSubtitle = document.getElementById('modal-subtitle');
    const modalLink = document.getElementById('modal-link');

    function openModalFromCard(card){
      modalTitle.textContent = card.dataset.title;
      modalSubtitle.textContent = card.querySelector('h3').textContent;
      modalDesc.textContent = card.dataset.desc;
      modalImage.src = card.dataset.images;
      modalLink.href = '#';
      modalTech.innerHTML = '';
      const tags = card.querySelectorAll('.tag');
      tags.forEach(t=>{
        const li = document.createElement('li'); li.textContent = t.textContent; modalTech.appendChild(li);
      });
      modal.classList.add('open');
      modal.setAttribute('aria-hidden','false');
      // trap focus quickly
      document.getElementById('close-modal').focus();
    }

    cards.forEach(c => {
      c.addEventListener('click', ()=>openModalFromCard(c));
      c.addEventListener('keydown', (e)=>{ if(e.key === 'Enter' || e.key === ' ') openModalFromCard(c); });
    });

    document.getElementById('close-modal').addEventListener('click', ()=>{
      modal.classList.remove('open');
      modal.setAttribute('aria-hidden','true');
    });

    // contact form tiny validation
    document.getElementById('send-btn').addEventListener('click', ()=>{
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const message = document.getElementById('message').value.trim();
      const fb = document.getElementById('form-feedback');
      if(!name || !email || !message){ fb.textContent = 'Please fill required fields.'; return; }
      fb.textContent = 'Thanks! I will get back to you soon.';
      // NOTE: Integrate email service here (Formspree / Netlify Forms / backend)
      setTimeout(()=>{ fb.textContent = ''; }, 5000);
    });

    // keyboard close modal
    document.addEventListener('keydown', (e)=>{ if(e.key === 'Escape') { modal.classList.remove('open'); modal.setAttribute('aria-hidden','true'); } });

    // small: prefers-reduced-motion respect
    const prefersReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
    if(prefersReduced){ document.querySelectorAll('.card').forEach(c=>c.style.transition = 'none'); }
  </script></body>
</html>
