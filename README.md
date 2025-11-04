# Portfolio_website
<!--
Amruta Patil - Modern Editable Portfolio (Single-file)
---------------------------------------------------
INSTRUCTIONS:
1) This is a single editable HTML file. Open in VS Code and edit text, images, links or styles directly.
2) Replace placeholder images found in the `data-img` attributes or replace the <img> src with your own path.
3) Edit the CSS variables under :root to change colors, fonts, spacing, or switch to dark mode.
4) Sections are clearly commented (HERO, SERVICES, ABOUT, PROJECTS, TESTIMONIALS, CONTACT, FOOTER).
5) Save as `index.html`. Use Live Server extension to preview locally.

Design notes:
- Light theme inspired by your reference with bold name and small transforming tagline line animation.
- Everything is kept editable: text, images, icons, project cards and links.

Enjoy — edit freely!
-->

<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Amruta Patil — Portfolio</title>
  <meta name="description" content="Portfolio of Amruta Patil — Data Analysis | AI | Full-Stack Development">
  
  <!-- Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700;800&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    /* ================= THEME VARIABLES (EDIT HERE) ================= */
    :root{
      --bg: #f7f9fc;              /* page background */
      --card: #ffffff;            /* card background */
      --muted: #6b7280;          /* muted text */
      --accent: #6c63ff;         /* primary accent */
      --accent-2: #ffb86b;       /* secondary accent */
      --accent-3: #00b894;       /* tertiary */
      --shadow: 0 8px 30px rgba(16,24,40,0.08);
      --radius: 16px;
      --max-width: 1200px;
    }

    /* ================ RESET ================ */
    *{box-sizing:border-box}
    html,body{height:100%}
    body{margin:0;background:var(--bg);font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto;color:#111827}
    a{color:inherit}

    .wrap{max-width:var(--max-width);margin:0 auto;padding:28px}

    /* ================ NAV ================ */
    header{display:flex;align-items:center;justify-content:space-between;gap:12px;padding:14px 0}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:44px;height:44px;border-radius:10px;background:linear-gradient(135deg,var(--accent),var(--accent-2));display:flex;align-items:center;justify-content:center;color:white;font-weight:800;font-family:Montserrat}
    nav a{margin-left:18px;text-decoration:none;color:var(--muted);font-weight:600}
    nav a.cta{background:linear-gradient(90deg,var(--accent),var(--accent-2));color:white;padding:10px 14px;border-radius:12px}

    /* ================ HERO ================ */
    .hero{display:grid;grid-template-columns:1fr 460px;gap:32px;align-items:center;margin-top:12px}
    .hero-left{padding:28px;background:linear-gradient(180deg,rgba(255,255,255,1),rgba(255,255,255,0.98));border-radius:var(--radius);box-shadow:var(--shadow)}
    .transform-line{font-family:Montserrat;font-size:14px;font-weight:700;letter-spacing:1px;color:var(--accent);display:inline-block;padding:8px 12px;border-radius:999px;background:linear-gradient(90deg,rgba(108,99,255,0.08),rgba(255,184,107,0.06));margin-bottom:18px}
    .name{font-family:Montserrat;font-size:48px;line-height:1;margin:0;color:#0f172a}
    .small-tag{font-size:18px;color:var(--muted);margin-top:8px}
    .lead{margin-top:18px;color:#374151}

    .hero-cta{margin-top:22px;display:flex;gap:12px}
    .btn-primary{background:linear-gradient(90deg,var(--accent),var(--accent-2));color:white;padding:12px 18px;border-radius:12px;text-decoration:none;font-weight:700}
    .btn-outline{border:1px solid rgba(15,23,42,0.06);padding:12px 18px;border-radius:12px;text-decoration:none;color:var(--muted);font-weight:700}

    .hero-right{position:relative}
    .profile-card{background:linear-gradient(180deg, #fff, #fff);padding:18px;border-radius:20px;box-shadow:var(--shadow);display:flex;gap:18px;align-items:center}
    .profile-pic{width:140px;height:140px;border-radius:18px;overflow:hidden;flex-shrink:0}
    .profile-pic img{width:100%;height:100%;object-fit:cover;display:block}
    .profile-meta{flex:1}
    .profile-meta h4{margin:0;font-size:20px}
    .profile-meta p{margin:6px 0 0;color:var(--muted)}

    /* subtle decorative blobs */
    .blob{position:absolute;right:-30px;top:-30px;width:220px;height:220px;border-radius:50%;background:linear-gradient(135deg, rgba(108,99,255,0.12), rgba(255,184,107,0.08));filter:blur(20px);z-index:-1}

    /* ================ SECTIONS ================ */
    section{margin-top:28px}
    .card{background:var(--card);padding:20px;border-radius:14px;box-shadow:var(--shadow)}

    /* Services */
    .services{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
    .service{padding:20px;border-radius:12px;border:1px solid rgba(15,23,42,0.04)}
    .service h5{margin:0 0 8px}
    .service p{margin:0;color:var(--muted)}

    /* Projects grid */
    .projects{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:18px;margin-top:14px}
    .project{border-radius:12px;overflow:hidden;border:1px solid rgba(15,23,42,0.04);background:linear-gradient(180deg, #fff, #fff)}
    .project img{width:100%;height:160px;object-fit:cover;display:block}
    .project-body{padding:12px}
    .project-body h4{margin:0 0 8px}
    .project-body p{margin:0;color:var(--muted);font-size:14px}

    /* Testimonials */
    .testimonials{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
    .testimonial{padding:18px;border-radius:12px;background:linear-gradient(90deg,rgba(255,255,255,0.6),rgba(255,255,255,0.4));border:1px solid rgba(15,23,42,0.03)}

    /* Contact */
    .contact-grid{display:grid;grid-template-columns:1fr 360px;gap:18px}
    label{display:block;margin:8px 0 6px;color:var(--muted);font-weight:600}
    input,textarea{width:100%;padding:12px;border-radius:8px;border:1px solid rgba(15,23,42,0.06);background:transparent}
    .send{background:linear-gradient(90deg,var(--accent),var(--accent-2));color:white;padding:12px 16px;border-radius:10px;border:0;font-weight:700}

    /* Footer */
    footer{margin-top:40px;text-align:center;color:var(--muted);font-size:14px;padding:18px}

    /* responsive */
    @media (max-width:980px){
      .hero{grid-template-columns:1fr}
      .services{grid-template-columns:1fr}
      .testimonials{grid-template-columns:1fr}
      .contact-grid{grid-template-columns:1fr}
    }

    /* small animation for transforming line */
    .transform-line span{display:inline-block;animation:move 6s linear infinite}
    @keyframes move{
      0%{transform:translateX(0)}
      50%{transform:translateX(6px)}
      100%{transform:translateX(0)}
    }

  </style>
</head>
<body>
  <div class="wrap">

    <!-- NAV -->
    <header>
      <div class="brand">
        <div class="logo">AP</div>
        <div>
          <div style="font-weight:800">Amruta Patil</div>
          <div style="font-size:12px;color:var(--muted)">Data Science • AI • Full-Stack</div>
        </div>
      </div>
      <nav>
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#projects">Portfolio</a>
        <a href="#contact">Contact</a>
        <a class="cta" href="#contact">Download CV</a>
        <a href="Amruta_Patil_Resume.docx" download class="cv-button">📄 Download CV</a>

      </nav>
    </header>

    <!-- HERO -->
    <main id="home" class="hero">
      <div class="hero-left">
        <div class="transform-line" aria-hidden="true"><span>Transforming Data into Intelligent Solutions</span></div>
        <h1 class="name">Amruta Patil</h1>
        <div class="small-tag">Data Science Enthusiast | Developer | Innovator</div>
        <p class="lead">I build AI-driven applications and data pipelines that solve real-world problems. Experienced in Python, Flask, MongoDB, MERN and data visualization. Recent projects include GazeGuard (eye recognition attendance), SmartBucket, AI-IDS and Emotion Detection from Speech.</p>

        <div class="hero-cta">
          <a class="btn-primary" href="#projects">View Projects</a>
          <a class="btn-outline" href="#contact">Hire Me</a>
        </div>

        <div style="margin-top:18px;display:flex;gap:12px;flex-wrap:wrap">
          <div style="background:#fff;padding:8px 12px;border-radius:10px;font-weight:700;color:var(--muted);border:1px solid rgba(15,23,42,0.04)">Python</div>
          <div style="background:#fff;padding:8px 12px;border-radius:10px;font-weight:700;color:var(--muted);border:1px solid rgba(15,23,42,0.04)">Flask</div>
          <div style="background:#fff;padding:8px 12px;border-radius:10px;font-weight:700;color:var(--muted);border:1px solid rgba(15,23,42,0.04)">MongoDB</div>
          <div style="background:#fff;padding:8px 12px;border-radius:10px;font-weight:700;color:var(--muted);border:1px solid rgba(15,23,42,0.04)">MERN</div>
        </div>
      </div>

      <div class="hero-right">
        <div class="blob" aria-hidden="true"></div>
        <div class="profile-card">
          <div class="profile-pic">
            <!-- Editable placeholder image: Replace this src with your photo -->
            <img src="https://i.postimg.cc/25RwKkyw/professphoto.jpg" alt="Profile photo" id="hero-photo">
          </div>
          <div class="profile-meta">
            <h4>Amruta Patil</h4>
            <p>Aspiring Data Scientist — B.Tech (CS & Business Systems), JSPM's RSCOE</p>
            <p style="margin-top:8px;color:var(--muted)"><strong>Internship:</strong> Deloitte Australia — Data Analytics Virtual Internship (July 2025)</p>
          </div>
        </div>
      </div>
    </main>
    <section id="certificates" class="certificates-section">
  <h2 class="section-title">🏅 Certificates & Achievements</h2>

  <!-- <a href="Certificates.pdf" class="cta" download>📄 View Certificates</a> -->
  <a href="Certificates" download class="cv-button">Certificates</a>
  
  <!-- <div class="certificates-container">
    <div class="certificate-card">
      <img src="assets/cert1.jpg" alt="Certificate 1">
      <h3>Deloitte Data Analytics Virtual Internship</h3>
      <p>Completed on July 10th, 2025 under Deloitte Australia.</p>
    </div>

    <div class="certificate-card">
      <img src="assets/cert2.jpg" alt="Certificate 2">
      <h3>Python for Data Science</h3>
      <p>Certified by IBM Skills Network.</p>
    </div>

    <div class="certificate-card">
      <img src="assets/cert3.jpg" alt="Certificate 3">
      <h3>Machine Learning Fundamentals</h3>
      <p>Completed via Coursera specialization.</p>
    </div>
  </div>
</section> -->


    <!-- SERVICES -->
    <section id="services" class="card">
      <h3 style="margin:0 0 12px">Services</h3>
      <div class="services">
        <div class="service">
          <h5>Data Analysis</h5>
          <p>Exploratory data analysis, visualization, and actionable insights using Python and SPSS.</p>
        </div>
        <div class="service">
          <h5>Web & Backend Development</h5>
          <p>Full-stack apps with Flask & MongoDB, REST APIs, and front-end UIs (HTML/CSS/JS or MERN).</p>
        </div>
        <div class="service">
          <h5>AI & Project Development</h5>
          <p>Prototype AI systems — eye-recognition, intrusion detection, emotion detection and more.</p>
        </div>
      </div>
    </section>

    <!-- ABOUT + EDUCATION -->
    <section class="card" style="display:grid;grid-template-columns:2fr 1fr;gap:18px">
      <div>
        <h3 style="margin-top:0">About Me</h3>
        <p class="lead" style="margin-top:6px;color:var(--muted)">I'm passionate and curious B.Tech student with a strong interest in coding, data analysis, and database management. I built intelligent applications like GazeGuard and SmartBucket, combining creativity and technology to solve real-world problems.</p>

        <h4 style="margin-top:14px">Notable Projects</h4>
        <ul style="color:var(--muted)">
          <li><strong>GazeGuard:</strong> Eye recognition attendance system (Python, Flask, MongoDB)</li>
          <li><strong>SmartBucket:</strong> Dual-temperature storage system</li>
          <li><strong>AI-IDS:</strong> Machine-learning intrusion detection</li>
          <li><strong>Emotion Detection from Speech:</strong> Deep-learning speech emotion classifier</li>
        </ul>
      </div>

      <aside style="padding:18px;background:linear-gradient(90deg, #fff, #fff);border-radius:12px;box-shadow:var(--shadow)">
        <h4 style="margin-top:0">Education</h4>
        <p style="color:var(--muted);margin:6px 0">B.Tech in Computer Science and Business Systems — JSPM's RSCOE, Pune (Expected 2027) with current CGPA 9.42</p>
        <p style="color:var(--muted);margin:6px 0">12th — CB Gurukul, Bidar (2023) — 89%</p>
        <p style="color:var(--muted);margin:6px 0">10th — CBPHS, Kamalnagar (2021) — 95%</p>
      </aside>
    </section>

    <!-- PROJECTS -->
    <section id="projects">
      <h3 style="margin-bottom:12px">Projects</h3>
      <div class="projects">
        <!-- Editable project cards (replace images and text) -->
        <article class="project">
          <img src="https://images.unsplash.com/photo-1526378722549-3d2c240f5f8b?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=6d5f5b9df2d2c1b5b8a9f3a4e3f7a2b1" alt="GazeGuard">
          <div class="project-body">
            <h4>GazeGuard</h4>
            <p>Eye recognition attendance system using Python, Flask & MongoDB.</p>
          </div>
        </article>

        <article class="project">
          <img src="https://images.unsplash.com/photo-1581091012184-7b4d5f1ddc4f?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=aa2f3a9c5f6b7c8d9e0a1b2c3d4e5f6a" alt="SmartBucket">
          <div class="project-body">
            <h4>SmartBucket</h4>
            <p>Dual-temperature smart storage system for preserving food efficiently.</p>
          </div>
        </article>

        <article class="project">
          <img src="https://images.unsplash.com/photo-1556155092-490a1ba16284?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=5f6d7a8b9c0d1e2f3a4b5c6d7e8f9a0b" alt="Stock Market Analysis">
          <div class="project-body">
            <h4>Stock Market Analysis (SPSS)</h4>
            <p>Data visualization and trend analysis using IBM SPSS.</p>
          </div>
        </article>

        <article class="project">
          <img src="https://images.unsplash.com/photo-1587620962725-abab7fe55159?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=0f1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o" alt="Pick and Place">
          <div class="project-body">
            <h4>Pick-and-Place Robot Simulation</h4>
            <p>RoboDK simulation with TMC 500 automating pick-and-place tasks.</p>
          </div>
        </article>

        <article class="project">
          <img src="https://images.unsplash.com/photo-1519389950473-47ba0277781c?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o6p" alt="AI-IDS">
          <div class="project-body">
            <h4>AI-IDS</h4>
            <p>Machine learning–driven intrusion detection for network anomalies.</p>
          </div>
        </article>

        <article class="project">
          <img src="https://images.unsplash.com/photo-1524504388940-b1c1722653e1?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=9b8a7c6d5e4f3a2b1c0d9e8f7a6b5c4d" alt="Emotion Detection">
          <div class="project-body">
            <h4>Emotion Detection from Speech</h4>
            <p>Deep learning model to classify emotions from voice tone and pitch.</p>
          </div>
        </article>
      </div>
    </section>

    <!-- TESTIMONIALS -->
    <section style="margin-top:22px">
      <h3 style="margin-bottom:12px">Testimonials</h3>
      <div class="testimonials">
        <div class="testimonial">
          <p style="margin:0;color:var(--muted)">"Great work — delivered a clean prototype and solid analysis."</p>
          <p style="margin-top:12px;font-weight:700">— Dr. S. Sharma</p>
        </div>
        <div class="testimonial">
          <p style="margin:0;color:var(--muted)">"Amruta's attention to detail and persistence is exceptional."</p>
          <p style="margin-top:12px;font-weight:700">— Prof. R. Kulkarni</p>
        </div>
        <div class="testimonial">
          <p style="margin:0;color:var(--muted)">"Delivered an intuitive UI and robust backend for our prototype."</p>
          <p style="margin-top:12px;font-weight:700">— Team Lead, RoboDK Project</p>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="card" style="margin-top:22px">
      <h3 style="margin:0 0 12px">Contact</h3>
      <div class="contact-grid">
        <div>
          <p style="color:var(--muted)">Interested in working together? Send me a message or reach out via LinkedIn / GitHub.</p>

          <form id="contact-form">
            <label for="name">Name</label>
            <input id="name" name="name" placeholder="Your name" required>

            <label for="email">Email</label>
            <input id="email" name="email" type="email" placeholder="you@example.com" required>

            <label for="message">Message</label>
            <textarea id="message" name="message" rows="5" placeholder="Tell me about your project..." required></textarea>

            <div style="margin-top:12px">
              <button class="send" type="submit">Send Message</button>
            </div>
          </form>

          <div id="form-info" style="color:var(--muted);margin-top:10px;font-size:13px"></div>
        </div>

        <aside style="padding:18px;border-radius:12px;background:linear-gradient(180deg,#fff,#fff);box-shadow:var(--shadow)">
          <h4 style="margin-top:0">Contact Info</h4>
          <p style="color:var(--muted);margin:6px 0">📧 <a href="mailto:amrutapatil6509@gmail.com" style="color:var(--accent);text-decoration:none">amrutapatil6509@gmail.com</a></p>
          <p style="color:var(--muted);margin:6px 0">📞 9019581623</p>
          <p style="color:var(--muted);margin:6px 0">🔗 <a href="https://www.linkedin.com/in/amruta-patil-2bb7362b7?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank" style="color:var(--accent);text-decoration:none">LinkedIn</a></p>
          <p style="color:var(--muted);margin:6px 0">🐙 <a href="https://github.com/boostkidza" target="_blank" style="color:var(--accent);text-decoration:none">GitHub</a></p>
        </aside>
      </div>
    </section>

    <footer>
      <div style="max-width:var(--max-width);margin:28px auto 40px;color:var(--muted)">© <strong>Amruta Patil</strong> • Built for clarity & impact.</div>
    </footer>
  </div>

  <script>
    // Smooth navigation
    document.querySelectorAll('nav a').forEach(a => {
      a.addEventListener('click', e => {
        // allow anchor only
        if (a.getAttribute('href').startsWith('#')){
          e.preventDefault();
          const id = a.getAttribute('href');
          document.querySelector(id).scrollIntoView({behavior:'smooth'});
        }
      });
    });

    // Contact form: default opens mail client
    document.getElementById('contact-form').addEventListener('submit', function(e){
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const message = document.getElementById('message').value.trim();
      const subject = encodeURIComponent('Portfolio Contact from ' + name);
      const body = encodeURIComponent('Name: ' + name + '\nEmail: ' + email + '\n\n' + message);
      window.location.href = `mailto:amrutapatil6509@gmail.com?subject=${subject}&body=${body}`;
      document.getElementById('form-info').textContent = 'Opening your mail client...';
    });

    // Tip: Make images editable via drag-and-drop or by changing src attribute in HTML.

  </script>
</body>
</html>
