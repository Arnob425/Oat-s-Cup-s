<!doctype html>
<html lang="bn">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Scrollable Presentation — CCPC (Web)</title>
<style>
  :root{
    --bg:#071018; --card:#0f1418; --fg:#e9f1f7; --muted:#98a6b0; --accent:#63bfe6;
  }
  *{box-sizing:border-box}
  body{
    margin:0; font-family:ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif;
    background:linear-gradient(180deg,#071018 0%, #071722 100%); color:var(--fg); -webkit-font-smoothing:antialiased;
    line-height:1.6;
  }
  header{
    position:sticky; top:0; z-index:40; backdrop-filter: blur(6px) saturate(120%);
    background:rgba(5,8,12,0.55); border-bottom:1px solid rgba(255,255,255,0.04);
    padding:10px 16px; display:flex; gap:12px; align-items:center;
  }
  .brand{font-weight:800}
  .navspacer{flex:1}
  .btn{appearance:none;border:0;background:#0f161b;color:var(--fg);padding:8px 12px;border-radius:10px;cursor:pointer;border:1px solid rgba(255,255,255,.06)}
  .btn:active{transform:translateY(1px)}
  main{max-width:1100px;margin:28px auto;padding:0 16px}
  section.card{
    background:linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
    border:1px solid rgba(255,255,255,0.06); border-radius:16px; padding:20px; margin-bottom:20px;
    box-shadow:0 18px 50px rgba(0,0,0,0.45);
  }
  h1{margin:0 0 10px 0; font-size:clamp(20px,2.6vw,30px)}
  p.muted{color:var(--muted); margin:6px 0}
  .gallery{display:flex;gap:12px;flex-wrap:wrap}
  .placeholder{
    background:#081018;border-radius:12px;border:1px solid rgba(255,255,255,.04);
    min-width:200px; min-height:140px; flex:1 1 30%; position:relative; overflow:hidden; display:flex;align-items:center;justify-content:center;
  }
  .placeholder img{width:100%;height:100%;object-fit:cover;display:block}
  .ph-ui{position:absolute;left:8px;right:8px;bottom:8px;display:flex;gap:6px;align-items:center}
  .ph-ui input{flex:1;padding:8px 10px;border-radius:8px;border:1px solid rgba(255,255,255,.06);background:rgba(255,255,255,.02);color:var(--fg)}
  .ph-ui button{padding:8px 10px;border-radius:8px;border:0;background:var(--accent);color:#022;cursor:pointer}
  .hint{font-size:13px;color:var(--muted);margin-top:8px}

  /* Video card tweaks */
  .video-wrap{border-radius:12px;overflow:hidden;background:#000;border:1px solid rgba(255,255,255,.04)}
  video{width:100%;height:auto;max-height:64vh;display:block;background:#000}

  /* small screens */
  @media (max-width:640px){
    .ph-ui{flex-direction:column;left:8px;right:8px;bottom:8px}
    .ph-ui input{width:100%}
  }

  footer{max-width:1100px;margin:12px auto 28px;padding:12px 16px;color:var(--muted);text-align:center}
  a.link{color:var(--accent); text-decoration:none}
</style>
</head>
<body>

<header>
  <div class="brand">🌿 CCPC — Web Presentation (Scrollable)</div>
  <div class="navspacer"></div>
  <button class="btn" id="toTop">Top</button>
  <button class="btn" id="toGallery">Gallery</button>
  <button class="btn" id="toVideo">Watch Video</button>
</header>

<main>
  <!-- Slide 1: Intro -->
  <section class="card" id="intro">
    <h1>Key Environmental Insights at CCPC</h1>
    <p class="muted">Scroll down to navigate. You can paste image URLs into gallery placeholders — they'll load instantly.</p>
    <p>About CCPC: Established in 1961 and known for a green, serene campus with active sustainability programs.</p>
  </section>

  <!-- Slide 2: Environmental Commitment -->
  <section class="card" id="commitment">
    <h1>Environmental Commitment</h1>
    <div class="content">
      <ul>
        <li>Holistic approach to eco-friendly operations and education.</li>
        <li>Tree plantation programs and campus cleanliness drives.</li>
        <li>Student-led awareness initiatives across the campus.</li>
      </ul>
    </div>
  </section>

  <!-- Slide 3: Gallery (user-supplied image URLs) -->
  <section class="card" id="gallery">
    <h1>A Gallery of Green</h1>
    <p class="muted">Paste an image URL in any placeholder below and press ↵ Enter or the Load button. Images persist in your browser (localStorage).</p>

    <div class="gallery" id="galleryGrid">
      <!-- Placeholder template repeated 3 times -->
      <div class="placeholder" data-slot="1">
        <div class="emptyText">Image 1</div>
        <img style="display:none" alt="Gallery image 1"/>
        <div class="ph-ui">
          <input placeholder="Paste image URL..." class="img-url" />
          <button class="loadBtn">Load</button>
        </div>
      </div>

      <div class="placeholder" data-slot="2">
        <div class="emptyText">Image 2</div>
        <img style="display:none" alt="Gallery image 2"/>
        <div class="ph-ui">
          <input placeholder="Paste image URL..." class="img-url" />
          <button class="loadBtn">Load</button>
        </div>
      </div>

      <div class="placeholder" data-slot="3">
        <div class="emptyText">Image 3</div>
        <img style="display:none" alt="Gallery image 3"/>
        <div class="ph-ui">
          <input placeholder="Paste image URL..." class="img-url" />
          <button class="loadBtn">Load</button>
        </div>
      </div>
    </div>

    <p class="hint">Tip: Use direct image links (ending with .jpg, .png, .webp). If an image doesn't load, try opening the URL in a new tab first.</p>
  </section>

  <!-- Slide 4: Trees / Wildlife -->
  <section class="card" id="trees">
    <h1>The Vital Role of Trees</h1>
    <ul>
      <li>Clean Air Filters — absorb CO₂, release O₂.</li>
      <li>Natural Coolers — shade reduces heat.</li>
      <li>Water Management — reduce erosion and runoff.</li>
    </ul>
  </section>

  <!-- Slide 5: Video (2nd last) -->
  <section class="card" id="videoSlide">
    <h1>Now Let's Watch: CCPC Campus</h1>
    <div class="video-wrap">
      <video id="vid" playsinline controls preload="metadata" poster="">
        <source src="WhatsApp Video 2025-08-22 at 01.26.34_7aaac6ef.mp4" type="video/mp4">
        Your browser doesn't support HTML5 video.
      </video>
    </div>
    <div style="margin-top:10px;display:flex;gap:8px;flex-wrap:wrap;align-items:center">
      <button class="btn" id="playBtn">▶ Play</button>
      <button class="btn" id="pauseBtn">⏸ Pause</button>
      <button class="btn" id="replayBtn">⟲ Replay</button>
      <button class="btn" id="fsBtn">⛶ Fullscreen</button>
      <div style="flex:1"></div>
      <label class="muted" style="font-size:13px" id="videoTime">00:00 / 00:00</label>
    </div>
    <p class="hint">If your video is local, keep it in the same folder as this HTML file OR click the "Open File" browser button (not provided here) to load a local file.</p>
  </section>

  <!-- Last slide -->
  <section class="card" id="thanks">
    <h1>Thank You!</h1>
    <p><strong>Team Contributions</strong></p>
    <ul>
      <li><strong>Tahsin Aman Chy</strong> — PPT Designer</li>
      <li><strong>Arnob Barua</strong> — Visual Content</li>
    </ul>
    <p class="muted">Contact: green.campus@ccpc.edu</p>
  </section>
</main>

<footer>
  Built for CCPC • Paste image URLs into the gallery placeholders to replace images.
</footer>

<script>
/* Smooth anchors for the header buttons */
document.getElementById('toTop').addEventListener('click', ()=> window.scrollTo({top:0, behavior:'smooth'}));
document.getElementById('toGallery').addEventListener('click', ()=> document.getElementById('gallery').scrollIntoView({behavior:'smooth'}));
document.getElementById('toVideo').addEventListener('click', ()=> document.getElementById('videoSlide').scrollIntoView({behavior:'smooth'}));

/* Gallery image loader (supports paste or manual URL) */
(function(){
  const placeholders = Array.from(document.querySelectorAll('.placeholder'));
  const STORAGE_KEY = 'webpres_gallery_v1';

  // load from storage
  const saved = JSON.parse(localStorage.getItem(STORAGE_KEY) || '{}');
  placeholders.forEach(ph => {
    const slot = ph.dataset.slot;
    const img = ph.querySelector('img');
    const empty = ph.querySelector('.emptyText');
    const input = ph.querySelector('.img-url');
    const btn = ph.querySelector('.loadBtn');

    // restore
    if(saved[slot]){
      img.src = saved[slot];
      img.style.display = 'block';
      empty.style.display = 'none';
      input.value = saved[slot];
    }

    // load function
    function loadFromInput(){
      const url = input.value.trim();
      if(!url) return;
      // quick check for data or http
      img.onerror = ()=> { alert('Image failed to load — check the URL or try another.'); img.style.display='none'; empty.style.display='block'; }
      img.onload = ()=> { img.style.display='block'; empty.style.display='none'; saved[slot]=url; localStorage.setItem(STORAGE_KEY, JSON.stringify(saved)); }
      img.src = url;
    }

    // events
    btn.addEventListener('click', loadFromInput);
    input.addEventListener('keydown', (e)=>{ if(e.key==='Enter') loadFromInput(); });

    // allow paste directly into page to auto-detect
    input.addEventListener('paste', (e)=> {
      setTimeout(()=> loadFromInput(), 10);
    });
  });

  // also allow dropping image URLs directly onto a placeholder
  placeholders.forEach(ph=>{
    ph.addEventListener('dragover', e=> e.preventDefault());
    ph.addEventListener('drop', e=> {
      e.preventDefault();
      const text = (e.dataTransfer.getData('text/plain') || '').trim();
      if(!text) return;
      const input = ph.querySelector('.img-url');
      input.value = text;
      ph.querySelector('.loadBtn').click();
    });
  });
})();

/* Video controls */
(function(){
  const vid = document.getElementById('vid');
  const playBtn = document.getElementById('playBtn');
  const pauseBtn = document.getElementById('pauseBtn');
  const replayBtn = document.getElementById('replayBtn');
  const fsBtn = document.getElementById('fsBtn');
  const timeLabel = document.getElementById('videoTime');

  function fmt(t){ if(!isFinite(t)) return '00:00'; const m = Math.floor(t/60).toString().padStart(2,'0'); const s = Math.floor(t%60).toString().padStart(2,'0'); return m+':'+s; }
  function update(){ timeLabel.textContent = fmt(vid.currentTime) + ' / ' + fmt(vid.duration); }

  if(vid){
    playBtn.onclick = ()=> vid.play();
    pauseBtn.onclick = ()=> vid.pause();
    replayBtn.onclick = ()=> { vid.currentTime = 0; vid.play(); };
    fsBtn.onclick = ()=> { if(document.fullscreenElement) document.exitFullscreen(); else vid.requestFullscreen().catch(()=>{}); };

    vid.addEventListener('timeupdate', update);
    vid.addEventListener('loadedmetadata', update);
    // save last time to localStorage per video src
    setInterval(()=> {
      try{
        const key = 'video_lasttime:' + (vid.currentSrc || 'default');
        localStorage.setItem(key, String(vid.currentTime || 0));
      }catch(e){}
    }, 1500);
    // restore if available
    vid.addEventListener('loadedmetadata', ()=> {
      try{
        const key = 'video_lasttime:' + (vid.currentSrc || 'default');
        const last = +localStorage.getItem(key) || 0;
        if(last>0 && last < vid.duration - 2) vid.currentTime = last;
      }catch(e){}
    });
  }
})();

/* small UX: allow the user to paste an image URL anywhere and press Ctrl+Shift+G to open Gallery */
window.addEventListener('keydown', (e)=>{
  if(e.ctrlKey && e.shiftKey && e.key.toLowerCase()==='g'){
    document.getElementById('gallery').scrollIntoView({behavior:'smooth'});
  }
});
</script>
</body>
</html>
