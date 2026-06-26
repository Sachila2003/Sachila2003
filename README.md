<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sachila Geeth — Profile</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { background: #0a0a0f; font-family: 'Segoe UI', sans-serif; overflow-x: hidden; }
  .scene {
    width: 100%; min-height: 100vh;
    background: radial-gradient(ellipse at 20% 50%, #0d1b2a 0%, #0a0a0f 60%);
    position: relative; overflow: hidden;
  }
  .grid-bg {
    position: absolute; inset: 0;
    background-image: linear-gradient(rgba(0,200,255,0.06) 1px, transparent 1px), linear-gradient(90deg, rgba(0,200,255,0.06) 1px, transparent 1px);
    background-size: 40px 40px;
    transform: perspective(600px) rotateX(60deg) translateY(60%);
    animation: gridMove 8s linear infinite;
  }
  @keyframes gridMove { 0% { background-position: 0 0; } 100% { background-position: 0 40px; } }
  .particle { position: absolute; border-radius: 50%; animation: floatUp linear infinite; opacity: 0; }
  @keyframes floatUp {
    0%   { transform: translateY(100vh) scale(0); opacity: 0; }
    10%  { opacity: 0.6; } 90% { opacity: 0.3; }
    100% { transform: translateY(-20vh) scale(1.5); opacity: 0; }
  }
  .orb { position: absolute; border-radius: 50%; filter: blur(80px); animation: pulse 4s ease-in-out infinite alternate; }
  @keyframes pulse { from { transform: scale(1); opacity: 0.4; } to { transform: scale(1.2); opacity: 0.6; } }
  .card-wrap {
    position: relative; z-index: 10;
    display: flex; flex-direction: column; align-items: center;
    padding: 48px 20px 60px; perspective: 1200px;
  }
  .card-3d {
    width: 100%; max-width: 680px;
    transform-style: preserve-3d;
    animation: float3d 6s ease-in-out infinite;
    transition: transform 0.1s ease-out;
  }
  @keyframes float3d {
    0%,100% { transform: rotateX(2deg) rotateY(-2deg) translateY(0); }
    33%      { transform: rotateX(-1deg) rotateY(2deg) translateY(-10px); }
    66%      { transform: rotateX(2deg) rotateY(-1deg) translateY(-5px); }
  }
  .card {
    background: linear-gradient(135deg, rgba(255,255,255,0.05) 0%, rgba(255,255,255,0.02) 100%);
    border: 1px solid rgba(0,200,255,0.2); border-radius: 24px;
    backdrop-filter: blur(20px); padding: 40px 36px 36px;
    box-shadow: 0 0 60px rgba(0,200,255,0.08), 0 40px 80px rgba(0,0,0,0.6), inset 0 1px 0 rgba(255,255,255,0.1);
    position: relative; overflow: hidden;
  }
  .card::before {
    content: ''; position: absolute; top: -50%; left: -60%; width: 40%; height: 200%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.04), transparent);
    animation: shine 5s ease-in-out infinite; transform: skewX(-20deg);
  }
  @keyframes shine { 0%,100% { left: -60%; } 50% { left: 120%; } }
  .card::after {
    content: ''; position: absolute; top: 0; left: 10%; right: 10%; height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,200,255,0.7), rgba(120,80,255,0.7), transparent);
    animation: lineGlow 3s ease-in-out infinite alternate;
  }
  @keyframes lineGlow { from { opacity: 0.5; } to { opacity: 1; } }
  .avatar-ring {
    width: 96px; height: 96px; border-radius: 50%; margin: 0 auto 20px;
    background: conic-gradient(from 0deg, #00c8ff, #7850ff, #ff3da6, #00c8ff);
    padding: 3px; animation: spin 4s linear infinite;
    box-shadow: 0 0 30px rgba(0,200,255,0.4);
  }
  @keyframes spin { from { filter: hue-rotate(0deg); } to { filter: hue-rotate(360deg); } }
  .avatar-inner {
    width: 100%; height: 100%; border-radius: 50%;
    background: linear-gradient(135deg, #0d1b2a, #131828);
    display: flex; align-items: center; justify-content: center;
    font-size: 32px; font-weight: 700; color: #00c8ff; letter-spacing: -1px;
  }
  .name {
    font-size: 28px; font-weight: 700; text-align: center;
    background: linear-gradient(90deg, #00c8ff, #7850ff, #ff3da6);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text; margin-bottom: 6px;
    animation: gradShift 4s linear infinite; background-size: 200%;
  }
  @keyframes gradShift { 0% { background-position: 0%; } 100% { background-position: 200%; } }
  .tagline {
    font-size: 11px; color: rgba(255,255,255,0.4); text-align: center;
    letter-spacing: 1.2px; text-transform: uppercase; margin-bottom: 20px;
  }
  .main-position {
    background: linear-gradient(135deg, rgba(0,200,255,0.1), rgba(120,80,255,0.1));
    border: 1px solid rgba(0,200,255,0.3); border-radius: 16px; padding: 16px 20px; margin-bottom: 10px;
    display: flex; align-items: center; gap: 14px; position: relative; overflow: hidden;
  }
  .main-position::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,200,255,0.6), rgba(120,80,255,0.6), transparent);
  }
  .position-icon {
    width: 44px; height: 44px; border-radius: 12px; flex-shrink: 0;
    background: linear-gradient(135deg, #0080ff, #7850ff);
    display: flex; align-items: center; justify-content: center;
    font-size: 20px; box-shadow: 0 4px 16px rgba(0,128,255,0.3);
  }
  .position-info { flex: 1; }
  .position-title { font-size: 15px; font-weight: 600; color: #fff; margin-bottom: 2px; }
  .position-company { font-size: 13px; color: #00c8ff; font-weight: 500; margin-bottom: 3px; }
  .position-meta { font-size: 11px; color: rgba(255,255,255,0.35); }
  .full-time-badge {
    font-size: 10px; font-weight: 700; letter-spacing: 1px; text-transform: uppercase;
    padding: 3px 10px; border-radius: 20px;
    background: linear-gradient(135deg, #0080ff, #7850ff); color: #fff;
    box-shadow: 0 2px 10px rgba(0,128,255,0.3); flex-shrink: 0;
  }
  .part-position {
    background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px; padding: 12px 16px; margin-bottom: 22px;
    display: flex; align-items: center; gap: 12px;
  }
  .part-icon {
    width: 36px; height: 36px; border-radius: 10px; flex-shrink: 0;
    background: rgba(120,80,255,0.15); border: 1px solid rgba(120,80,255,0.2);
    display: flex; align-items: center; justify-content: center; font-size: 16px;
  }
  .part-info { flex: 1; }
  .part-title { font-size: 13px; font-weight: 500; color: rgba(255,255,255,0.7); margin-bottom: 2px; }
  .part-company { font-size: 12px; color: rgba(120,80,255,0.8); }
  .part-time-badge {
    font-size: 10px; font-weight: 600; letter-spacing: 0.8px; text-transform: uppercase;
    padding: 3px 9px; border-radius: 20px;
    border: 1px solid rgba(120,80,255,0.3); color: rgba(120,80,255,0.8);
    background: rgba(120,80,255,0.08); flex-shrink: 0;
  }
  .divider { height: 1px; margin: 0 0 22px; background: linear-gradient(90deg, transparent, rgba(255,255,255,0.08), transparent); }
  .stats-row { display: flex; gap: 8px; margin-bottom: 22px; }
  .stat-card {
    flex: 1; padding: 16px 10px; border-radius: 14px; text-align: center;
    border: 1px solid rgba(255,255,255,0.06); background: rgba(255,255,255,0.02);
    transition: transform 0.3s, border-color 0.3s; position: relative; overflow: hidden;
  }
  .stat-card::before { content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 2px; opacity: 0; transition: opacity 0.3s; }
  .stat-card:hover { transform: translateY(-5px); border-color: rgba(0,200,255,0.2); }
  .stat-card:hover::before { opacity: 1; }
  .sc-blue::before   { background: linear-gradient(90deg, #0080ff, #00c8ff); }
  .sc-purple::before { background: linear-gradient(90deg, #7850ff, #ff3da6); }
  .sc-pink::before   { background: linear-gradient(90deg, #ff3da6, #ffaa44); }
  .sc-green::before  { background: linear-gradient(90deg, #00c864, #00c8ff); }
  .stat-num { font-size: 22px; font-weight: 700; line-height: 1; margin-bottom: 5px; }
  .stat-lbl { font-size: 9px; color: rgba(255,255,255,0.35); text-transform: uppercase; letter-spacing: 1px; line-height: 1.3; }
  .info-row { display: flex; gap: 10px; margin-bottom: 22px; flex-wrap: wrap; }
  .info-chip {
    flex: 1; min-width: 130px; background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px; padding: 12px 14px; transition: border-color 0.3s, background 0.3s;
  }
  .info-chip:hover { border-color: rgba(0,200,255,0.3); background: rgba(0,200,255,0.05); }
  .chip-label { font-size: 10px; color: rgba(255,255,255,0.3); margin-bottom: 4px; letter-spacing: 0.8px; text-transform: uppercase; }
  .chip-value { font-size: 12px; color: rgba(255,255,255,0.8); font-weight: 500; }
  .section-head {
    font-size: 10px; color: rgba(255,255,255,0.3); letter-spacing: 2px;
    text-transform: uppercase; margin-bottom: 12px; display: flex; align-items: center; gap: 8px;
  }
  .section-head::after { content: ''; flex: 1; height: 1px; background: linear-gradient(90deg, rgba(255,255,255,0.06), transparent); }
  .stack-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(76px, 1fr)); gap: 7px; margin-bottom: 22px; }
  .tech-pill {
    padding: 8px 5px; border-radius: 10px; text-align: center;
    font-size: 10px; font-weight: 600; border: 1px solid transparent; cursor: default;
    transition: transform 0.25s, box-shadow 0.25s; animation: techIn 0.5s both;
  }
  .tech-pill:hover { transform: translateY(-3px) scale(1.05); }
  @keyframes techIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }
  .dot-icon { font-size: 15px; display: block; margin-bottom: 2px; }
  .t-blue   { background: rgba(0,120,255,0.12); border-color: rgba(0,120,255,0.25); color: #4da6ff; }
  .t-blue:hover   { box-shadow: 0 4px 20px rgba(0,120,255,0.25); }
  .t-cyan   { background: rgba(0,200,255,0.10); border-color: rgba(0,200,255,0.25); color: #00c8ff; }
  .t-cyan:hover   { box-shadow: 0 4px 20px rgba(0,200,255,0.25); }
  .t-purple { background: rgba(120,80,255,0.12); border-color: rgba(120,80,255,0.25); color: #a884ff; }
  .t-purple:hover { box-shadow: 0 4px 20px rgba(120,80,255,0.25); }
  .t-green  { background: rgba(0,200,100,0.10); border-color: rgba(0,200,100,0.25); color: #00c864; }
  .t-green:hover  { box-shadow: 0 4px 20px rgba(0,200,100,0.20); }
  .t-orange { background: rgba(255,140,0,0.10); border-color: rgba(255,140,0,0.25); color: #ffaa44; }
  .t-orange:hover { box-shadow: 0 4px 20px rgba(255,140,0,0.20); }
  .t-red    { background: rgba(255,60,60,0.10); border-color: rgba(255,60,60,0.20); color: #ff7070; }
  .t-red:hover    { box-shadow: 0 4px 20px rgba(255,60,60,0.15); }
  .t-pink   { background: rgba(255,60,150,0.10); border-color: rgba(255,60,150,0.20); color: #ff6ea8; }
  .t-pink:hover   { box-shadow: 0 4px 20px rgba(255,60,150,0.15); }
  .t-teal   { background: rgba(0,180,160,0.10); border-color: rgba(0,180,160,0.25); color: #00c8b4; }
  .t-teal:hover   { box-shadow: 0 4px 20px rgba(0,180,160,0.15); }
  .currently {
    background: linear-gradient(135deg, rgba(0,200,255,0.06), rgba(120,80,255,0.06));
    border: 1px solid rgba(0,200,255,0.15); border-radius: 14px;
    padding: 14px 16px; margin-bottom: 22px; display: flex; align-items: center; gap: 12px;
  }
  .live-dot {
    width: 9px; height: 9px; border-radius: 50%; background: #00ff88; flex-shrink: 0;
    box-shadow: 0 0 8px #00ff88, 0 0 16px rgba(0,255,136,0.4);
    animation: blink 1.4s ease-in-out infinite;
  }
  @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0.3; } }
  .currently-text { font-size: 12px; color: rgba(255,255,255,0.65); line-height: 1.5; }
  .currently-text strong { color: #00c8ff; font-weight: 600; }
  .cta-row { display: flex; gap: 8px; flex-wrap: wrap; }
  .btn {
    flex: 1; min-width: 110px; padding: 11px 14px; border-radius: 12px;
    font-size: 12px; font-weight: 600; cursor: pointer; border: none;
    transition: transform 0.2s, box-shadow 0.2s; text-align: center;
    text-decoration: none; display: inline-flex; align-items: center; justify-content: center; gap: 5px;
  }
  .btn-primary { background: linear-gradient(135deg, #0080ff, #7850ff); color: #fff; box-shadow: 0 4px 20px rgba(0,128,255,0.3); }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(0,128,255,0.5); }
  .btn-secondary { background: rgba(255,255,255,0.04); color: rgba(255,255,255,0.65); border: 1px solid rgba(255,255,255,0.1); }
  .btn-secondary:hover { background: rgba(255,255,255,0.08); transform: translateY(-2px); }
</style>
</head>
<body>
<div class="scene">
  <div class="orb" style="width:300px;height:300px;background:rgba(0,128,255,0.12);top:-80px;left:-60px;animation-duration:5s;"></div>
  <div class="orb" style="width:200px;height:200px;background:rgba(120,80,255,0.15);top:40%;right:-40px;animation-duration:7s;animation-delay:-2s;"></div>
  <div class="orb" style="width:250px;height:250px;background:rgba(255,60,150,0.08);bottom:-50px;left:30%;animation-duration:6s;animation-delay:-1s;"></div>
  <div class="grid-bg"></div>
  <div id="particles"></div>
  <div class="card-wrap">
    <div class="card-3d" id="card3d">
      <div class="card">
        <div class="avatar-ring"><div class="avatar-inner">SG</div></div>
        <div class="name">Sachila Geeth</div>
        <div class="tagline">Software Engineer &nbsp;&middot;&nbsp; Full-Stack Developer &nbsp;&middot;&nbsp; UI/UX Enthusiast</div>
        <div class="main-position">
          <div class="position-icon">&#127970;</div>
          <div class="position-info">
            <div class="position-title">Associate Software Engineer</div>
            <div class="position-company">Technovity FZC LLC</div>
            <div class="position-meta">Sharjah Publishing City, UAE &#127462;&#127466;</div>
          </div>
          <div class="full-time-badge">Full-Time</div>
        </div>
        <div class="part-position">
          <div class="part-icon">&#9889;</div>
          <div class="part-info">
            <div class="part-title">Full-Stack Developer</div>
            <div class="part-company">Fullstack Craft</div>
          </div>
          <div class="part-time-badge">Part-Time</div>
        </div>
        <div class="divider"></div>
        <div class="section-head">Experience at a Glance</div>
        <div class="stats-row">
          <div class="stat-card sc-blue">
            <div class="stat-num" style="background:linear-gradient(135deg,#00c8ff,#0080ff);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">1.5+</div>
            <div class="stat-lbl">Years Industry Exp.</div>
          </div>
          <div class="stat-card sc-purple">
            <div class="stat-num" style="background:linear-gradient(135deg,#7850ff,#ff3da6);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">10+</div>
            <div class="stat-lbl">Production Level Products</div>
          </div>
          <div class="stat-card sc-pink">
            <div class="stat-num" style="background:linear-gradient(135deg,#ff3da6,#ffaa44);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">50+</div>
            <div class="stat-lbl">Projects Delivered</div>
          </div>
          <div class="stat-card sc-green">
            <div class="stat-num" style="background:linear-gradient(135deg,#00c864,#00c8ff);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">2</div>
            <div class="stat-lbl">Companies</div>
          </div>
        </div>
        <div class="info-row">
          <div class="info-chip">
            <div class="chip-label">Specialized in</div>
            <div class="chip-value">React.js &middot; Node.js &middot; Laravel</div>
          </div>
          <div class="info-chip">
            <div class="chip-label">Mobile</div>
            <div class="chip-value">React Native &#128241;</div>
          </div>
          <div class="info-chip">
            <div class="chip-label">Portfolio</div>
            <div class="chip-value">sachilageeth.dev &#127760;</div>
          </div>
        </div>
        <div class="currently">
          <div class="live-dot"></div>
          <div class="currently-text">
            Building with <strong>Next.js</strong> + <strong>Laravel</strong> &amp; <strong>PostgreSQL</strong> &mdash; stored procedures &amp; DB functions for high-performance backends.
          </div>
        </div>
        <div class="section-head">Core Tech Stack</div>
        <div class="stack-grid" id="stack"></div>
        <div class="section-head">Connect</div>
        <div class="cta-row">
          <a class="btn btn-primary" href="https://sachilageeth.dev" target="_blank">&#127760; Portfolio</a>
          <a class="btn btn-secondary" href="https://www.linkedin.com/in/sachila-geeth-094576344/" target="_blank">&#128188; LinkedIn</a>
          <a class="btn btn-secondary" href="https://www.facebook.com/share/1D45HqeUav/" target="_blank">&#128216; Facebook</a>
          <a class="btn btn-secondary" href="https://www.instagram.com/_the.sachi_" target="_blank">&#128247; Instagram</a>
          <a class="btn btn-secondary" href="mailto:sachilageeth@gmail.com">&#9993; Email</a>
        </div>
      </div>
    </div>
  </div>
</div>
<script>
  const pContainer = document.getElementById('particles');
  const colors = ['#00c8ff','#7850ff','#ff3da6','#00ff88','#ffaa44'];
  for (let i = 0; i < 24; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    const size = Math.random() * 4 + 2;
    p.style.cssText = 'width:'+size+'px;height:'+size+'px;left:'+(Math.random()*100)+'%;background:'+colors[Math.floor(Math.random()*colors.length)]+';animation-duration:'+(Math.random()*8+6)+'s;animation-delay:'+(Math.random()*8)+'s;';
    pContainer.appendChild(p);
  }
  const techs = [
    { name:'Next.js',      cls:'t-blue',   icon:'&#11043;' },
    { name:'React',        cls:'t-cyan',   icon:'&#9883;'  },
    { name:'Laravel',      cls:'t-red',    icon:'&#128314;'},
    { name:'Node.js',      cls:'t-green',  icon:'&#9672;'  },
    { name:'PostgreSQL',   cls:'t-blue',   icon:'&#128024;'},
    { name:'MongoDB',      cls:'t-green',  icon:'&#127807;'},
    { name:'Tailwind',     cls:'t-cyan',   icon:'&#128168;'},
    { name:'TypeScript',   cls:'t-blue',   icon:'TS'       },
    { name:'React Native', cls:'t-purple', icon:'&#128241;'},
    { name:'PHP',          cls:'t-purple', icon:'&#128024;'},
    { name:'Firebase',     cls:'t-orange', icon:'&#128293;'},
    { name:'Figma',        cls:'t-pink',   icon:'&#10022;' },
    { name:'MySQL',        cls:'t-teal',   icon:'&#128452;'},
    { name:'Git',          cls:'t-orange', icon:'&#9678;'  },
    { name:'Express',      cls:'t-teal',   icon:'&#9889;'  },
  ];
  const grid = document.getElementById('stack');
  techs.forEach(function(t, i) {
    const el = document.createElement('div');
    el.className = 'tech-pill ' + t.cls;
    el.style.animationDelay = (i * 0.05) + 's';
    el.innerHTML = '<span class="dot-icon">' + t.icon + '</span>' + t.name;
    grid.appendChild(el);
  });
  const card3d = document.getElementById('card3d');
  document.addEventListener('mousemove', function(e) {
    card3d.style.animation = 'none';
    const cx = window.innerWidth / 2, cy = window.innerHeight / 2;
    const dx = (e.clientX - cx) / cx, dy = (e.clientY - cy) / cy;
    card3d.style.transform = 'rotateX('+(-dy*5)+'deg) rotateY('+(dx*6)+'deg) translateY('+(-dy*5)+'px)';
  });
  document.addEventListener('mouseleave', function() {
    card3d.style.animation = 'float3d 6s ease-in-out infinite';
  });
</script>
</body>
</html>
