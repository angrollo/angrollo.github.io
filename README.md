[index.html](https://github.com/user-attachments/files/30414683/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Angelo Carollo — Theoretical Physics</title>
<meta name="description" content="Angelo Carollo, theoretical physicist at the University of Palermo — quantum optics, critical quantum metrology, and dissipative phase transitions.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,300;9..144,400;9..144,500;9..144,600&family=Inter:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --void:#0E1B2A;
    --panel:#16283D;
    --panel-2:#1C3149;
    --paper:#EDE6D6;
    --paper-dim:#E2D9C4;
    --ink:#1B1B18;
    --brass:#C9A227;
    --brass-dim:#9c8028;
    --teal:#5FB3AA;
    --line: rgba(237,230,214,0.14);
    --maxw: 1040px;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--void);
    color:var(--paper);
    font-family:'Inter', sans-serif;
    font-size:16px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3{
    font-family:'Fraunces', serif;
    font-weight:500;
    letter-spacing:-0.01em;
    margin:0;
  }
  .mono{ font-family:'IBM Plex Mono', monospace; }
  a{ color:inherit; }
  .wrap{ max-width:var(--maxw); margin:0 auto; padding:0 28px; }

  /* NAV */
  nav.top{
    position:sticky; top:0; z-index:50;
    backdrop-filter: blur(10px);
    background:rgba(14,27,42,0.82);
    border-bottom:1px solid var(--line);
  }
  nav.top .wrap{
    display:flex; align-items:center; justify-content:space-between;
    height:64px;
  }
  .brand{
    font-family:'Fraunces', serif; font-size:1.05rem; font-weight:600;
    letter-spacing:0.02em;
  }
  .brand span{ color:var(--brass); }
  .navlinks{ display:flex; gap:28px; font-size:0.86rem; }
  .navlinks a{
    text-decoration:none; color:var(--paper-dim); opacity:0.85;
    padding:6px 0; border-bottom:1px solid transparent;
    transition: opacity .2s, border-color .2s;
  }
  .navlinks a:hover{ opacity:1; border-color:var(--brass); }
  .navtoggle{ display:none; }

  /* HERO */
  header.hero{
    position:relative;
    padding:120px 0 96px;
    overflow:hidden;
    border-bottom:1px solid var(--line);
  }
  header.hero .wrap{ position:relative; z-index:2; }
  .eyebrow{
    font-family:'IBM Plex Mono', monospace;
    text-transform:uppercase; letter-spacing:0.16em; font-size:0.72rem;
    color:var(--teal); margin-bottom:22px; display:block;
  }
  h1.display{
    font-size:clamp(2.6rem, 6vw, 4.4rem);
    line-height:1.03;
    max-width:14ch;
    color:var(--paper);
  }
  h1.display em{
    font-style:italic; color:var(--brass); font-weight:400;
  }
  .lede{
    max-width:52ch; margin-top:28px; font-size:1.08rem;
    color:var(--paper-dim);
  }
  .hero-actions{ display:flex; gap:16px; margin-top:38px; flex-wrap:wrap; }
  .btn{
    display:inline-flex; align-items:center; gap:8px;
    padding:12px 22px; border-radius:2px; font-size:0.86rem;
    text-decoration:none; font-family:'IBM Plex Mono', monospace;
    border:1px solid var(--line); transition: all .2s;
  }
  .btn.primary{ background:var(--brass); color:var(--void); border-color:var(--brass); font-weight:500;}
  .btn.primary:hover{ background:var(--brass-dim); }
  .btn.ghost{ color:var(--paper); }
  .btn.ghost:hover{ border-color:var(--brass); color:var(--brass); }

  .spiral-wrap{
    position:absolute; right:-60px; top:50%; transform:translateY(-50%);
    width:520px; height:520px; opacity:0.9; z-index:1;
  }
  @media (max-width:900px){ .spiral-wrap{ display:none; } }
  .spiral-path{
    stroke-dasharray: 2000;
    stroke-dashoffset: 2000;
    animation: draw 3.2s cubic-bezier(.4,0,.2,1) forwards;
  }
  .spiral-dot{
    animation: fade-in 1s ease 2.6s forwards;
    opacity:0;
  }
  @keyframes draw{ to{ stroke-dashoffset:0; } }
  @keyframes fade-in{ to{ opacity:1; } }
  @media (prefers-reduced-motion: reduce){
    .spiral-path{ stroke-dashoffset:0; animation:none; }
    .spiral-dot{ opacity:1; animation:none; }
  }

  /* SECTIONS */
  section{ padding:84px 0; border-bottom:1px solid var(--line); }
  section:last-of-type{ border-bottom:none; }
  .section-head{ display:flex; align-items:baseline; gap:18px; margin-bottom:44px; }
  .section-num{ font-family:'IBM Plex Mono', monospace; color:var(--teal); font-size:0.82rem; }
  .section-head h2{ font-size:1.9rem; }

  /* ABOUT */
  .about-grid{ display:grid; grid-template-columns: 1.3fr 1fr; gap:64px; align-items:start; }
  @media (max-width:800px){ .about-grid{ grid-template-columns:1fr; } }
  .about-grid p{ color:var(--paper-dim); margin:0 0 18px; }
  .about-grid p:last-child{ margin-bottom:0; }
  .facts{ display:grid; gap:0; border-top:1px solid var(--line); }
  .fact{
    display:flex; justify-content:space-between; padding:14px 0;
    border-bottom:1px solid var(--line); font-size:0.9rem;
  }
  .fact dt{ color:var(--paper-dim); }
  .fact dd{ margin:0; font-family:'IBM Plex Mono', monospace; color:var(--paper); text-align:right; }

  /* RESEARCH */
  .research-grid{ display:grid; grid-template-columns:repeat(3,1fr); gap:1px; background:var(--line); border:1px solid var(--line); }
  @media (max-width:760px){ .research-grid{ grid-template-columns:1fr; } }
  .research-card{ background:var(--void); padding:32px 28px; }
  .research-card h3{ font-size:1.08rem; color:var(--brass); margin-bottom:12px; font-weight:500; }
  .research-card p{ color:var(--paper-dim); font-size:0.92rem; margin:0; }

  /* PUBLICATIONS */
  .pub-list{ display:flex; flex-direction:column; }
  .pub{
    display:grid; grid-template-columns: 64px 1fr auto; gap:20px; align-items:start;
    padding:22px 0; border-bottom:1px solid var(--line);
  }
  .pub:first-child{ border-top:1px solid var(--line); }
  .pub-year{ font-family:'IBM Plex Mono', monospace; color:var(--teal); font-size:0.9rem; padding-top:2px; }
  .pub-title{ font-size:1.0rem; color:var(--paper); }
  .pub-venue{ display:block; margin-top:6px; color:var(--paper-dim); font-size:0.86rem; font-style:italic; }
  .pub-cite{ font-family:'IBM Plex Mono', monospace; font-size:0.8rem; color:var(--brass); white-space:nowrap; text-align:right; }
  @media (max-width:640px){
    .pub{ grid-template-columns: 1fr; gap:6px; }
    .pub-cite{ text-align:left; }
  }
  .see-more{ margin-top:28px; font-size:0.88rem; color:var(--paper-dim); }
  .see-more a{ color:var(--teal); text-decoration:underline; }

  /* METRICS STRIP */
  .metrics{ display:grid; grid-template-columns:repeat(4,1fr); gap:1px; background:var(--line); border:1px solid var(--line); margin-top:48px;}
  @media (max-width:700px){ .metrics{ grid-template-columns:repeat(2,1fr);} }
  .metric{ background:var(--panel); padding:26px 22px; text-align:left; }
  .metric .num{ font-family:'Fraunces', serif; font-size:2.1rem; color:var(--brass); }
  .metric .label{ font-family:'IBM Plex Mono', monospace; font-size:0.72rem; text-transform:uppercase; letter-spacing:0.08em; color:var(--paper-dim); margin-top:6px; }

  /* TEACHING / SERVICE */
  .two-col{ display:grid; grid-template-columns:1fr 1fr; gap:64px; }
  @media (max-width:800px){ .two-col{ grid-template-columns:1fr; gap:48px; } }
  ul.plain{ list-style:none; margin:0; padding:0; }
  ul.plain li{
    padding:14px 0; border-bottom:1px solid var(--line); font-size:0.92rem; color:var(--paper-dim);
    display:flex; justify-content:space-between; gap:16px;
  }
  ul.plain li span.tag{ font-family:'IBM Plex Mono', monospace; font-size:0.74rem; color:var(--teal); white-space:nowrap; }
  ul.plain li strong{ color:var(--paper); font-weight:500; }

  /* COLLABORATORS */
  .chips{ display:flex; flex-wrap:wrap; gap:10px; margin-top:28px; }
  .chip{
    border:1px solid var(--line); padding:8px 14px; border-radius:20px;
    font-size:0.82rem; color:var(--paper-dim);
  }

  /* CONTACT / FOOTER */
  footer{ padding:80px 0 60px; }
  .contact-grid{ display:grid; grid-template-columns:1.2fr 1fr; gap:48px; }
  @media (max-width:760px){ .contact-grid{ grid-template-columns:1fr; } }
  footer h2{ font-size:2rem; max-width:14ch; }
  .contact-list{ margin-top:28px; }
  .contact-row{
    display:flex; justify-content:space-between; padding:14px 0; border-top:1px solid var(--line);
    font-size:0.92rem;
  }
  .contact-row:last-child{ border-bottom:1px solid var(--line); }
  .contact-row a{ color:var(--brass); text-decoration:none; }
  .contact-row a:hover{ text-decoration:underline; }
  .foot-note{ margin-top:56px; color:var(--paper-dim); font-size:0.78rem; font-family:'IBM Plex Mono', monospace; opacity:0.6; }
</style>
</head>
<body>

<nav class="top">
  <div class="wrap">
    <div class="brand">A. <span>Carollo</span></div>
    <div class="navlinks">
      <a href="#about">About</a>
      <a href="#research">Research</a>
      <a href="#publications">Publications</a>
      <a href="#teaching">Teaching &amp; Service</a>
      <a href="#contact">Contact</a>
    </div>
  </div>
</nav>

<header class="hero">
  <div class="spiral-wrap" aria-hidden="true">
    <svg viewBox="0 0 520 520" width="520" height="520">
      <path class="spiral-path" d="M260,260
        m0,-2
        c 30,0 55,25 55,55
        c 0,44 -36,80 -80,80
        c -55,0 -100,-45 -100,-100
        c 0,-66 54,-120 120,-120
        c 77,0 140,63 140,140
        c 0,88 -72,160 -160,160
        c -99,0 -180,-81 -180,-180
        c 0,-110 90,-200 200,-200"
        fill="none" stroke="#C9A227" stroke-width="1.4" stroke-linecap="round"/>
      <circle class="spiral-dot" cx="260" cy="60" r="4" fill="#5FB3AA"/>
      <circle class="spiral-dot" cx="98" cy="258" r="3" fill="#EDE6D6" opacity="0.6"/>
    </svg>
  </div>
  <div class="wrap">
    <span class="eyebrow">Università degli Studi di Palermo — Dipartimento di Fisica e Chimica "E. Segrè"</span>
    <h1 class="display">The geometry of <em>quantum</em> systems, in and out of equilibrium.</h1>
    <p class="lede">I'm a theoretical physicist working on quantum optics, critical quantum metrology, and dissipative phase transitions — mostly asking what geometry and topology can tell us about many-body quantum systems that are open, driven, or far from equilibrium.</p>
    <div class="hero-actions">
      <a class="btn primary" href="#publications">View publications</a>
      <a class="btn ghost" href="#contact">Get in touch</a>
    </div>
  </div>
</header>

<section id="about">
  <div class="wrap">
    <div class="section-head"><span class="section-num">01</span><h2>About</h2></div>
    <div class="about-grid">
      <div>
        <p>I am a physicist at the University of Palermo, in the Department of Physics and Chemistry "Emilio Segrè," working within the theoretical physics group (FIS/02). My research sits at the intersection of quantum optics, open quantum systems, and many-body physics — with a recurring thread of geometry: Berry and Uhlmann phases, geometric measures of criticality, and the topology of lattice models.</p>
        <p>Current work centers on <strong style="color:var(--paper)">critical quantum sensing</strong> — using dissipative phase transitions as a resource for quantum-enhanced metrology — alongside longer-running interests in waveguide QED, non-Hermitian photonic baths, and topological phases of matter.</p>
        <p>I did my PhD at Imperial College London under Vladko Vedral, followed by postdoctoral positions at Cambridge, Innsbruck, and Palermo, with a period in computational finance research in between. I currently serve on the editorial boards of <em>Quantum</em>, <em>PLOS One</em>, and <em>Cogent Physics</em>.</p>
      </div>
      <dl class="facts">
        <div class="fact"><dt>Field</dt><dd>Theoretical Physics — FIS/02</dd></div>
        <div class="fact"><dt>PhD</dt><dd>Imperial College London, 2004</dd></div>
        <div class="fact"><dt>Habilitation</dt><dd>ASN I Fascia, 02/A2 &amp; 02/B2</dd></div>
        <div class="fact"><dt>ORCID</dt><dd>0000-0002-4402-2207</dd></div>
        <div class="fact"><dt>Languages</dt><dd>Italian, English (C1)</dd></div>
      </dl>
    </div>
  </div>
</section>

<section id="research">
  <div class="wrap">
    <div class="section-head"><span class="section-num">02</span><h2>Research</h2></div>
    <div class="research-grid">
      <div class="research-card">
        <h3>Critical Quantum Sensing</h3>
        <p>Exploiting dissipative and driven phase transitions as a resource for quantum metrology — from Uhlmann curvature to multi-parameter estimation in fermionic and bosonic Gaussian states.</p>
      </div>
      <div class="research-card">
        <h3>Geometric &amp; Topological Phases</h3>
        <p>Berry and Uhlmann phase in open and driven systems, decoherence-induced topological transitions, and the geometry of quantum phase transitions in lattice models.</p>
      </div>
      <div class="research-card">
        <h3>Waveguide &amp; Non-Hermitian QED</h3>
        <p>Dressed states and giant atoms in topological waveguide QED, and exotic emitter interactions mediated by non-Hermitian photonic baths.</p>
      </div>
      <div class="research-card">
        <h3>Open Quantum Many-Body Systems</h3>
        <p>Dissipative dynamics, metastability, and stochastic resonance in driven many-body quantum systems, including quantum trajectory approaches.</p>
      </div>
      <div class="research-card">
        <h3>Topological Phases of Matter</h3>
        <p>Finite-temperature geometric and topological properties of lattice models — the Kitaev honeycomb model, the Haldane model, and related spin systems.</p>
      </div>
      <div class="research-card">
        <h3>Quantum Thermodynamics &amp; Stochastic Systems</h3>
        <p>Noise-induced phenomena in metastable quantum and condensed-matter systems, memristive devices, and stochastic multistable dynamics.</p>
      </div>
    </div>

    <div class="metrics">
      <div class="metric"><div class="num">~50</div><div class="label">Peer-reviewed articles</div></div>
      <div class="metric"><div class="num">~2,275</div><div class="label">Citations (Scopus / WoS)</div></div>
      <div class="metric"><div class="num">24</div><div class="label">h-index (28 · Google Scholar)</div></div>
      <div class="metric"><div class="num">7</div><div class="label">Physical Review Letters</div></div>
    </div>
  </div>
</section>

<section id="publications">
  <div class="wrap">
    <div class="section-head"><span class="section-num">03</span><h2>Selected Publications</h2></div>
    <div class="pub-list">

      <div class="pub">
        <div class="pub-year mono">2020</div>
        <div>
          <div class="pub-title">Geometry of quantum phase transitions</div>
          <span class="pub-venue">Physics Reports, 838:1 — with D. Valenti &amp; B. Spagnolo</span>
        </div>
        <div class="pub-cite">IF 28.3 · 30 cit.</div>
      </div>

      <div class="pub">
        <div class="pub-year mono">2003</div>
        <div>
          <div class="pub-title">Geometric phase in open systems</div>
          <span class="pub-venue">Phys. Rev. Lett. 90, 160402 — with I. Fuentes-Guridi, M. França Santos &amp; V. Vedral</span>
        </div>
        <div class="pub-cite">247 cit.</div>
      </div>

      <div class="pub">
        <div class="pub-year mono">2005</div>
        <div>
          <div class="pub-title">Geometric phases and criticality in spin-chain systems</div>
          <span class="pub-venue">Phys. Rev. Lett. 95, 157203 — with J. K. Pachos</span>
        </div>
        <div class="pub-cite">191 cit.</div>
      </div>

      <div class="pub">
        <div class="pub-year mono">2004</div>
        <div>
          <div class="pub-title">Spin-1/2 geometric phase driven by decohering quantum fields</div>
          <span class="pub-venue">Phys. Rev. Lett. 92, 020402</span>
        </div>
        <div class="pub-cite">94 cit.</div>
      </div>

      <div class="pub">
        <div class="pub-year mono">2002</div>
        <div>
          <div class="pub-title">Vacuum induced spin-1/2 Berry's phase</div>
          <span class="pub-venue">Phys. Rev. Lett. 89, 220404 — with I. Fuentes-Guridi, S. Bose &amp; V. Vedral</span>
        </div>
        <div class="pub-cite">87 cit.</div>
      </div>

      <div class="pub">
        <div class="pub-year mono">2018</div>
        <div>
          <div class="pub-title">Uhlmann curvature in dissipative phase transitions</div>
          <span class="pub-venue">Scientific Reports 8, 9852 — with B. Spagnolo &amp; D. Valenti</span>
        </div>
        <div class="pub-cite">55 cit.</div>
      </div>

      <div class="pub">
        <div class="pub-year mono">2021</div>
        <div>
          <div class="pub-title">Vacancy-like dressed states in topological waveguide QED</div>
          <span class="pub-venue">Phys. Rev. Lett. 126, 063601 — with L. Leonforte &amp; F. Ciccarello</span>
        </div>
        <div class="pub-cite">IF 8.4 · 12 cit.</div>
      </div>

      <div class="pub">
        <div class="pub-year mono">2022</div>
        <div>
          <div class="pub-title">Exotic interactions mediated by a non-Hermitian photonic bath</div>
          <span class="pub-venue">Optica 9(5):565 — with F. Roccati, S. Lorenzo, G. Calajò, G. M. Palma &amp; F. Ciccarello</span>
        </div>
        <div class="pub-cite">IF 11.1</div>
      </div>

    </div>
    <p class="see-more">Full publication list on <a href="https://scholar.google.it/citations?user=1NqcriAAAAAJ&hl=it" target="_blank" rel="noopener">Google Scholar</a> and <a href="https://orcid.org/0000-0002-4402-2207" target="_blank" rel="noopener">ORCID</a>.</p>
  </div>
</section>

<section id="teaching">
  <div class="wrap">
    <div class="section-head"><span class="section-num">04</span><h2>Teaching &amp; Service</h2></div>
    <div class="two-col">
      <div>
        <h3 style="font-size:1.1rem; color:var(--brass); margin-bottom:18px;">Teaching</h3>
        <ul class="plain">
          <li><strong>Theory of General Relativity</strong><span class="tag">LM Fisica</span></li>
          <li><strong>Elementi di Interazione Radiazione/Materia</strong><span class="tag">Ottica e Optometria</span></li>
          <li><strong>Fisica II</strong><span class="tag">Ing. Biomedica</span></li>
          <li><strong>Stochastic Processes</strong><span class="tag">LM Sc. Statistiche</span></li>
          <li><strong>Quantum Optics and Topology in Lattice Models</strong><span class="tag">PhD</span></li>
          <li><strong>Topology in Condensed Matter</strong><span class="tag">PhD</span></li>
        </ul>
      </div>
      <div>
        <h3 style="font-size:1.1rem; color:var(--brass); margin-bottom:18px;">Editorial &amp; Professional Service</h3>
        <ul class="plain">
          <li><strong>Editorial Board</strong><span class="tag">Quantum</span></li>
          <li><strong>Editorial Board</strong><span class="tag">PLOS One</span></li>
          <li><strong>Editorial Board</strong><span class="tag">Cogent Physics</span></li>
          <li><strong>Referee</strong><span class="tag">PRL · PRX Quantum · Nat. Sci. Rep.</span></li>
          <li><strong>Co-organizer, NES2023</strong><span class="tag">Erice</span></li>
          <li><strong>Committee, IQIS2022</strong><span class="tag">Palermo</span></li>
        </ul>
      </div>
    </div>

    <h3 style="font-size:1.1rem; color:var(--brass); margin:52px 0 8px;">Selected International Collaborations</h3>
    <div class="chips">
      <div class="chip">Vlatko Vedral — Oxford</div>
      <div class="chip">Sougato Bose — UCL</div>
      <div class="chip">Rosario Fazio — ICTP Trieste</div>
      <div class="chip">Jiannis Pachos — Leeds</div>
      <div class="chip">Ivette Fuentes — Nottingham</div>
      <div class="chip">Igor Lesanovsky — Tübingen</div>
      <div class="chip">Alejandro González-Tudela — CSIC Madrid</div>
      <div class="chip">Harold Baranger — Duke</div>
      <div class="chip">Nikola Paunković — IST Lisbon</div>
      <div class="chip">Alexander Dubkov — Lobachevsky Univ.</div>
    </div>
  </div>
</section>

<footer id="contact">
  <div class="wrap">
    <div class="contact-grid">
      <div>
        <span class="eyebrow">Get in touch</span>
        <h2>Reach out about research, collaboration, or editorial matters.</h2>
      </div>
      <div class="contact-list">
        <div class="contact-row"><span>Email</span><a href="mailto:angelo.carollo@unipa.it">angelo.carollo@unipa.it</a></div>
        <div class="contact-row"><span>Department</span><span>Via Archirafi 36, 90123 Palermo, Italy</span></div>
        <div class="contact-row"><span>ORCID</span><a href="https://orcid.org/0000-0002-4402-2207" target="_blank" rel="noopener">0000-0002-4402-2207</a></div>
        <div class="contact-row"><span>Google Scholar</span><a href="https://scholar.google.it/citations?user=1NqcriAAAAAJ&hl=it" target="_blank" rel="noopener">View profile</a></div>
      </div>
    </div>
    <div class="foot-note">© Angelo Carollo — Università degli Studi di Palermo</div>
  </div>
</footer>

</body>
</html>
