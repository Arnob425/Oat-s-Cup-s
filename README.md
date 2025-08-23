<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>CCPC — Environmental Insights (Web Slides)</title>
  <meta name="description" content="Web version of the CCPC environmental presentation with slide navigation and a video on the 2nd last slide." />
  <style>
    :root{
      --bg:#0b0d10;--fg:#e8edf2;--muted:#a8b3bd;--card:#12171c;--ring:rgba(113,199,236,.4);--accent:#71c7ec
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{margin:0;background:radial-gradient(1200px 600px at 20% -10%,#111823,#0a0e13 60%,#070a0d 100%);color:var(--fg);font-family:ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif;overflow:hidden}
    .app{height:100%;display:flex;flex-direction:column}
    header{position:sticky;top:0;z-index:10;background:rgba(10,14,18,.45);backdrop-filter:saturate(140%) blur(8px);border-bottom:1px solid rgba(255,255,255,.06)}
    .nav{max-width:1200px;margin:auto;padding:10px 14px;display:flex;gap:10px;align-items:center}
    .brand{font-weight:800;letter-spacing:.2px}
    .spacer{flex:1}
    .btn{appearance:none;border:none;background:#151a20;border:1px solid rgba(255,255,255,.08);color:var(--fg);padding:8px 12px;border-radius:12px;cursor:pointer;transition:.2s;display:inline-flex;align-items:center;gap:8px}
    .btn:hover{transform:translateY(-1px);box-shadow:0 10px 28px rgba(0,0,0,.35)}
    .btn:focus{outline:none;box-shadow:0 0 0 6px var(--ring)}

    main{flex:1;display:grid;place-items:center}

    /* Slide container */
    .stage{position:relative;width:min(1100px,96vw);height:min(620px,78vh);border-radius:22px;background:linear-gradient(180deg,rgba(255,255,255,.06),rgba(255,255,255,.02));border:1px solid rgba(255,255,255,.08);box-shadow:0 20px 60px rgba(0,0,0,.45);overflow:hidden}
    .slide{position:absolute;inset:0;padding:28px 32px 22px 32px;display:grid;grid-template-rows:auto 1fr auto;gap:10px;opacity:0;transform:translateX(40px) scale(.98);transition:.35s ease;pointer-events:none}
    .slide.active{opacity:1;transform:none;pointer-events:auto}
    .title{font-size:clamp(22px,2.8vw,32px);font-weight:800;letter-spacing:.2px;margin:2px 0 8px 0}
    .content{overflow:auto;padding-right:6px}
    .content p{color:var(--fg);opacity:.95;line-height:1.65;margin:.4rem 0}
    .muted{color:var(--muted)}
    .bullets{display:grid;gap:.5rem;margin:.6rem 0 0 0}
    .bullets li{margin-left:1rem}

    /* Video slide */
    .video-wrap{position:relative;background:#000;border-radius:16px;overflow:hidden;border:1px solid rgba(255,255,255,.08)}
    video{display:block;width:100%;height:62vh;max-height:100%;background:#000}
    .vcontrols{display:flex;gap:8px;flex-wrap:wrap;margin-top:10px}
    .range{width:240px}

    /* Pager */
    .pager{position:absolute;left:0;right:0;bottom:10px;display:flex;justify-content:center;gap:8px}
    .dot{width:8px;height:8px;border-radius:999px;background:rgba(255,255,255,.25);transition:.2s}
    .dot.active{background:var(--accent);box-shadow:0 0 0 6px rgba(113,199,236,.25)}

    /* Footer row inside slide */
    .row{display:flex;align-items:center;gap:10px}
    .row .spacer{flex:1}

    /* Mobile tweaks */
    @media (max-width:720px){
      .stage{height:min(78vh,620px)}
      video{height:46vh}
      .range{width:140px}
    }
  </style>
</head>
<body>
  <div class="app">
    <header>
      <div class="nav">
        <div class="brand">🌿 CCPC — Environmental Insights</div>
        <div class="spacer"></div>
        <button class="btn" id="prevBtn">← Prev</button>
        <button class="btn" id="nextBtn">Next →</button>
      </div>
    </header>

    <main>
      <div class="stage" id="stage">
        <!-- Slides start -->
        <section class="slide active" data-title="Key Environmental Insights at CCPC">
          <h1 class="title">Key Environmental Insights at CCPC</h1>
          <div class="content">
            <p class="muted">Explore CCPC's dedication to preserving and enhancing its natural surroundings. This web presentation mirrors the slide deck.</p>
            <p><strong>About CCPC:</strong> Established in 1961 and known for a green, serene campus with active sustainability programs.</p>
          </div>
          <div class="row">
            <div class="muted">Use ← / → or buttons to navigate</div>
            <div class="spacer"></div>
            <div id="slideCount" class="muted"></div>
          </div>
        </section>

        <section class="slide" data-title="Environmental Commitment">
          <h1 class="title">Information About CCPC's Environmental Commitment</h1>
          <div class="content">
            <ul class="bullets">
              <li>Holistic approach to eco‑friendly operations and education.</li>
              <li>Tree plantation programs and campus cleanliness drives.</li>
              <li>Student‑led awareness initiatives across the campus.</li>
            </ul>
          </div>
          <div class="row"><div class="muted">Commitment & programs overview</div></div>
        </section>

        <section class="slide" data-title="Accolades for Environmental Leadership">
          <h1 class="title">Accolades for Environmental Leadership</h1>
          <div class="content">
            <ol class="bullets">
              <li><strong>Recognized Excellence:</strong> "Green Campus" award for sustainability practices.</li>
              <li><strong>A Collaborative Effort:</strong> Students, faculty, staff, and partners contributed.</li>
              <li><strong>Inspiring Future Generations:</strong> Strengthening resolve to innovate and educate.</li>
            </ol>
          </div>
          <div class="row"><div class="muted">Recognition highlights</div></div>
        </section>

        <section class="slide" data-title="Campus Beauty: Nature's Embrace">
          <h1 class="title">Campus Beauty: Nature's Embrace</h1>
          <div class="content">
            <p>CCPC's campus showcases majestic trees, rolling lawns, and serene pathways, framed by scenic hills — a tranquil setting for learning and reflection.</p>
          </div>
          <div class="row"><div class="muted">Landscape & serenity</div></div>
        </section>

        <section class="slide" data-title="A Gallery of Green">
          <h1 class="title">A Gallery of Green: Scenes from CCPC</h1>
          <div class="content">
            <p>Add photos here (replace the placeholders below).</p>
            <div class="row" style="gap:10px;flex-wrap:wrap">
              <div style="flex:1;min-width:180px;height:140px;background:#0a0f13;border:1px solid rgba(255,255,255,.08);border-radius:12px"></div>
              <div style="flex:1;min-width:180px;height:140px;background:#0a0f13;border:1px solid rgba(255,255,255,.08);border-radius:12px"></div>
              <div style="flex:1;min-width:180px;height:140px;background:#0a0f13;border:1px solid rgba(255,255,255,.08);border-radius:12px"></div>
            </div>
          </div>
          <div class="row"><div class="muted">Replace with campus photos</div></div>
        </section>

        <section class="slide" data-title="The Vital Role of Trees">
          <h1 class="title">The Vital Role of Trees: Nature's Pillars</h1>
          <div class="content">
            <ul class="bullets">
              <li><strong>Clean Air Filters</strong> — absorb CO₂, release O₂, improve air quality.</li>
              <li><strong>Natural Coolers</strong> — provide shade and reduce heat, lowering cooling needs.</li>
              <li><strong>Water Management</strong> — reduce erosion and manage stormwater runoff.</li>
            </ul>
          </div>
          <div class="row"><div class="muted">Ecosystem services</div></div>
        </section>

        <section class="slide" data-title="Trees: A Haven for Wildlife">
          <h1 class="title">Trees: A Haven for Wildlife</h1>
          <div class="content">
            <ul class="bullets">
              <li><strong>Deer</strong> — shelter and forage among dense foliage.</li>
              <li><strong>Foxes</strong> — roam edges, hunt small prey, forage fruits.</li>
              <li><strong>Snakes</strong> — control rodent populations; vital but often unseen.</li>
            </ul>
          </div>
          <div class="row"><div class="muted">Biodiversity on campus</div></div>
        </section>

        <section class="slide" data-title="Wild Boar: Guardians of the Forest Floor">
          <h1 class="title">Wild Boar: Guardians of the Forest Floor</h1>
          <div class="content">
            <ul class="bullets">
              <li><strong>Natural Tillers</strong> — soil turnover aids seed dispersal & regeneration.</li>
              <li><strong>Pest Control</strong> — consume insects and small rodents.</li>
              <li><strong>Biodiversity Support</strong> — create microhabitats while foraging.</li>
            </ul>
          </div>
          <div class="row"><div class="muted">Ecological roles</div></div>
        </section>

        <section class="slide" data-title="Our Green Planet at Risk">
          <h1 class="title">Our Green Planet at Risk: The Impact of Human Unconsciousness</h1>
          <div class="content"><p>Human negligence threatens ecosystems through pollution, overuse of resources, and habitat loss. Awareness and action are essential.</p></div>
          <div class="row"><div class="muted">Challenges & awareness</div></div>
        </section>

        <section class="slide" data-title="Deforestation: A Global Challenge">
          <h1 class="title">Deforestation: A Global Challenge</h1>
          <div class="content"><p>Forest loss worldwide disrupts climate stability, biodiversity, and local livelihoods. Understanding drivers is key to solutions.</p></div>
          <div class="row"><div class="muted">Global perspective</div></div>
        </section>

        <section class="slide" data-title="The Scale and Consequences of Deforestation">
          <h1 class="title">The Scale and Consequences of Deforestation</h1>
          <div class="content"><p>Consequences include increased greenhouse gases, soil degradation, altered rainfall patterns, and species extinctions.</p></div>
          <div class="row"><div class="muted">Impacts</div></div>
        </section>

        <section class="slide" data-title="Why Forests Matter">
          <h1 class="title">Why Forests Matter: Climate, Biodiversity, and People</h1>
          <div class="content">
            <ul class="bullets">
              <li>Carbon sinks that moderate global warming.</li>
              <li>Habitats supporting diverse life forms.</li>
              <li>Resources and cultural value for communities.</li>
            </ul>
          </div>
          <div class="row"><div class="muted">Value of forests</div></div>
        </section>

        <section class="slide" data-title="Main Drivers of Deforestation">
          <h1 class="title">Main Drivers of Deforestation</h1>
          <div class="content">
            <ul class="bullets">
              <li>Agricultural expansion and monocultures.</li>
              <li>Logging and fuelwood demand.</li>
              <li>Infrastructure and urban sprawl.</li>
            </ul>
          </div>
          <div class="row"><div class="muted">Root causes</div></div>
        </section>

        <section class="slide" data-title="Solutions: From Policy to Personal Action">
          <h1 class="title">Solutions: From Policy to Personal Action</h1>
          <div class="content">
            <ul class="bullets">
              <li>Stronger forest governance and protected areas.</li>
              <li>Restoration, reforestation, and sustainable sourcing.</li>
              <li>Community education and daily lifestyle changes.</li>
            </ul>
          </div>
          <div class="row"><div class="muted">Action pathways</div></div>
        </section>

        <!-- SECOND LAST: Video slide -->
        <section class="slide" data-title="CCPC Campus Video">
          <h1 class="title">Now Let's Watch: CCPC Campus</h1>
          <div class="content">
            <div class="video-wrap">
              <video id="vid" playsinline controls preload="metadata" poster="">
                <!-- Put your video file in the same folder or update the src below -->
                <source src="WhatsApp Video 2025-08-22 at 01.26.34_7aaac6ef.mp4" type="video/mp4" />
              </video>
            </div>
            <div class="vcontrols">
              <button class="btn" id="playBtn">▶️ Play</button>
              <button class="btn" id="pauseBtn">⏸️ Pause</button>
              <button class="btn" id="replayBtn">⟲ Replay</button>
              <button class="btn" id="pipBtn">🗔 Picture‑in‑Picture</button>
              <button class="btn" id="fsBtn">⛶ Fullscreen</button>
              <input id="seek" class="range" type="range" min="0" max="100" step="0.1" value="0" />
              <input id="vol" class="range" type="range" min="0" max="1" step="0.02" value="1" />
            </div>
            <p class="muted" id="timeTxt">00:00 / 00:00</p>
          </div>
          <div class="row"><div class="muted">Use fullscreen for best experience</div></div>
        </section>

        <!-- LAST: Thank you / team slide -->
        <section class="slide" data-title="Team & Contact">
          <h1 class="title">Thank You!</h1>
          <div class="content">
            <p><strong>Team Contributions</strong></p>
            <ul class="bullets">
              <li><strong>Tahsin Aman Chy</strong> — PowerPoint Presentation Designer (Class 09, Section BS‑B, Roll 28)</li>
              <li><strong>Arnob Barua</strong> — Picture/Visual Content Contributor (Class 09, Section BS‑B, Roll 26)</li>
            </ul>
            <p class="muted">Learn more: ccpc.edu/sustainability • Contact: green.campus@ccpc.edu</p>
          </div>
          <div class="row"><div class="muted">End slide</div></div>
        </section>
        <!-- Slides end -->

        <div class="pager" id="pager"></div>
      </div>
    </main>
  </div>

  <script>
    // --- Slide system ---
    const slides = Array.from(document.querySelectorAll('.slide'));
    const pager = document.getElementById('pager');
    const prevBtn = document.getElementById('prevBtn');
    const nextBtn = document.getElementById('nextBtn');
    const slideCount = document.getElementById('slideCount');
    let i = 0;

    function syncHash(){ location.hash = '#'+(i+1); }
    function go(n){
      i = Math.max(0, Math.min(slides.length-1, n));
      slides.forEach((s,idx)=> s.classList.toggle('active', idx===i));
      updateDots();
      if(slideCount) slideCount.textContent = `${i+1} / ${slides.length}`;
      syncHash();
    }

    function next(){ go(i+1) }
    function prev(){ go(i-1) }

    // Dots
    function buildDots(){
      pager.innerHTML = '';
      slides.forEach((_,idx)=>{
        const d = document.createElement('div');
        d.className = 'dot';
        d.title = 'Slide '+(idx+1);
        d.addEventListener('click', ()=>go(idx));
        pager.appendChild(d);
      });
    }
    function updateDots(){
      const dots = Array.from(pager.children);
      dots.forEach((d,idx)=> d.classList.toggle('active', idx===i));
    }

    // Keyboard & touch
    window.addEventListener('keydown', (e)=>{
      if(['ArrowRight','PageDown',' '].includes(e.key)) { e.preventDefault(); next(); }
      if(['ArrowLeft','PageUp'].includes(e.key)) { e.preventDefault(); prev(); }
      if(e.key==='Home'){ go(0) }
      if(e.key==='End'){ go(slides.length-1) }
    });

    let touchX=null;
    window.addEventListener('touchstart', (e)=>{ touchX = e.touches[0].clientX; }, {passive:true});
    window.addEventListener('touchend', (e)=>{
      if(touchX==null) return;
      const dx = (e.changedTouches[0].clientX - touchX);
      if(Math.abs(dx) > 40) { dx<0 ? next() : prev(); }
      touchX=null;
    }, {passive:true});

    // Start on hash slide if present
    const start = Math.max(1, parseInt(location.hash.replace('#',''))||1);
    buildDots();
    go(start-1);

    // --- Video controls (2nd last slide) ---
    const vid = document.getElementById('vid');
    const playBtn = document.getElementById('playBtn');
    const pauseBtn = document.getElementById('pauseBtn');
    const replayBtn = document.getElementById('replayBtn');
    const pipBtn = document.getElementById('pipBtn');
    const fsBtn = document.getElementById('fsBtn');
    const seek = document.getElementById('seek');
    const vol = document.getElementById('vol');
    const timeTxt = document.getElementById('timeTxt');

    function fmt(t){ if(!isFinite(t)) return '00:00'; const m=Math.floor(t/60).toString().padStart(2,'0'); const s=Math.floor(t%60).toString().padStart(2,'0'); return `${m}:${s}` }
    function updateTime(){ timeTxt.textContent = `${fmt(vid.currentTime)} / ${fmt(vid.duration)}`; seek.max = vid.duration||100; seek.value = vid.currentTime||0 }

    if(vid){
      playBtn.onclick = ()=> vid.play();
      pauseBtn.onclick = ()=> vid.pause();
      replayBtn.onclick = ()=> { vid.currentTime = 0; vid.play(); };
      fsBtn.onclick = ()=> { if(document.fullscreenElement){ document.exitFullscreen(); } else { vid.requestFullscreen().catch(()=>{}); } };
      pipBtn.onclick = async ()=> { try { if(document.pictureInPictureElement){ document.exitPictureInPicture(); } else if(document.pictureInPictureEnabled){ await vid.requestPictureInPicture(); } } catch(e){} };
      seek.oninput = ()=> vid.currentTime = +seek.value;
      vol.oninput = ()=> vid.volume = +vol.value;
      vid.addEventListener('timeupdate', updateTime);
      vid.addEventListener('loadedmetadata', updateTime);
    }
  </script>
</body>
</html>
