<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>For My Alee 💗</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@500;700&family=Great+Vibes&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    min-height:100vh;
    font-family:'Poppins',sans-serif;
    overflow-x:hidden;
    background:
      radial-gradient(circle at 18% 8%, #fff0f8 0%, transparent 55%),
      radial-gradient(circle at 85% 12%, #ffd9ee 0%, transparent 52%),
      linear-gradient(160deg,#ffe0f0 0%,#ffc4e0 32%,#ff9ecb 65%,#ff86bf 100%);
    background-attachment:fixed;
  }

  /* ---------- floating background hearts ---------- */
  .bg-hearts{position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden;}
  .heart{
    position:absolute;bottom:-70px;
    animation:floatUp linear infinite;
    filter:drop-shadow(0 6px 10px rgba(255,105,180,.35));
  }
  @keyframes floatUp{
    0%  {transform:translateY(0) rotate(-15deg) scale(.7);opacity:0;}
    12% {opacity:var(--o,.8);}
    85% {opacity:var(--o,.8);}
    100%{transform:translateY(-118vh) rotate(20deg) scale(1.15);opacity:0;}
  }

  /* ---------- layout ---------- */
  main{
    position:relative;z-index:2;
    min-height:100vh;
    display:flex;flex-direction:column;align-items:center;
    padding:38px 16px 70px;
  }

  /* ---------- bouquet ---------- */
  .bouquet-wrap{
    position:relative;
    width:min(560px,92vw);
    height:430px;
  }
  .sway{
    position:absolute;inset:0;
    transform-origin:50% 100%;
    animation:sway 7s ease-in-out infinite;
  }
  @keyframes sway{
    0%,100%{transform:rotate(-1.4deg);}
    50%    {transform:rotate(1.4deg);}
  }
  .glow{
    position:absolute;left:50%;top:46%;
    width:540px;height:540px;margin:-270px 0 0 -270px;
    border-radius:50%;
    background:radial-gradient(circle,rgba(255,255,255,.9),rgba(255,182,220,.55) 42%,transparent 72%);
    filter:blur(12px);
    animation:pulse 5s ease-in-out infinite;
  }
  @keyframes pulse{
    0%,100%{transform:scale(1);opacity:.85;}
    50%    {transform:scale(1.09);opacity:1;}
  }
  .bouquet{position:absolute;inset:0;}

  /* stems */
  .stem{
    position:absolute;left:50%;bottom:0;
    width:7px;margin-left:-3.5px;
    border-radius:4px;
    background:linear-gradient(90deg,#8ad18b,#3f8f4f);
    transform-origin:50% 100%;
    z-index:1;
  }

  /* leaves */
  .leaf{
    position:absolute;left:50%;bottom:0;
    width:70px;height:30px;
    background:linear-gradient(120deg,#a3e79a,#4aa85f);
    border-radius:0 100% 0 100%;
    box-shadow:inset -2px -3px 7px rgba(0,0,0,.10);
    transform-origin:50% 100%;
    z-index:4;
  }

  /* the bouquet wrap (cone) */
  .wrap{
    position:absolute;left:50%;bottom:0;
    width:215px;height:215px;
    transform:translateX(-50%);
    clip-path:polygon(50% 100%, 2% 0%, 98% 0%);
    background:
      repeating-linear-gradient(115deg,rgba(255,255,255,.38) 0 9px,transparent 9px 26px),
      linear-gradient(160deg,#ffa5d2 0%,#ff5fa8 55%,#e63a86 100%);
    filter:drop-shadow(0 14px 22px rgba(214,51,132,.38));
    z-index:3;
  }

  /* ribbon bow */
  .bow{
    position:absolute;left:50%;bottom:158px;
    width:120px;height:74px;margin-left:-60px;
    z-index:6;
  }
  .bow .loop{
    position:absolute;top:6px;width:52px;height:44px;
    border:7px solid #ff3f92;
    background:linear-gradient(180deg,rgba(255,255,255,.55),rgba(255,255,255,.05));
  }
  .bow .loop.left {left:2px;  border-radius:60% 40% 50% 50% / 62% 62% 38% 38%; transform:rotate(-12deg);}
  .bow .loop.right{right:2px; border-radius:40% 60% 50% 50% / 62% 62% 38% 38%; transform:rotate(12deg);}
  .bow .knot{
    position:absolute;left:50%;top:13px;width:22px;height:25px;margin-left:-11px;
    border-radius:9px;
    background:linear-gradient(180deg,#ff77b6,#e8277d);
    box-shadow:inset 0 -3px 5px rgba(0,0,0,.18);
  }
  .bow .tail{
    position:absolute;top:36px;width:14px;height:36px;border-radius:4px;
    background:linear-gradient(180deg,#ff5fa8,#e8277d);
  }
  .bow .tail.t1{left:36px;  transform:rotate(18deg);}
  .bow .tail.t2{right:36px; transform:rotate(-18deg);}

  /* flowers */
  .flower{
    position:absolute;left:50%;bottom:0;
    width:0;height:0;
    transform:translate(var(--x),var(--y)) rotate(var(--r,0deg)) scale(var(--s,1));
    z-index:5;
  }
  .petal{
    position:absolute;
    left:-12px;top:-33px;
    width:24px;height:33px;
    border-radius:50% 50% 46% 46% / 62% 62% 38% 38%;
    background:
      radial-gradient(circle at 50% 88%, rgba(255,255,255,.9), transparent 62%),
      var(--c,#ff9ecb);
    box-shadow:inset 0 -5px 9px rgba(199,42,120,.18);
    transform-origin:50% 100%;
    transform:rotate(calc(var(--i) * 45deg));
  }
  .core{
    position:absolute;left:-11px;top:-11px;
    width:22px;height:22px;border-radius:50%;
    background:radial-gradient(circle at 35% 30%,#fffbd1,#ffd54f 45%,#f0a51c 100%);
    box-shadow:0 3px 7px rgba(170,90,0,.28), inset 0 -3px 5px rgba(0,0,0,.15);
  }

  /* ---------- the letter ---------- */
  .letter{
    position:relative;z-index:20;
    width:min(690px,94vw);
    margin-top:-85px;
    padding:34px 30px 32px;
    text-align:center;
    border-radius:32px;
    background:linear-gradient(180deg,rgba(255,255,255,.94),rgba(255,243,250,.90));
    border:2px solid rgba(255,255,255,.95);
    box-shadow:
      0 26px 60px rgba(214,51,132,.30),
      inset 0 0 0 7px rgba(255,214,235,.55),
      inset 0 0 40px rgba(255,182,220,.35);
    backdrop-filter:blur(10px);
    -webkit-backdrop-filter:blur(10px);
  }
  .to{
    font-size:12px;letter-spacing:.42em;text-transform:uppercase;
    color:#c9457f;font-weight:600;
  }
  .letter h1{
    font-family:'Dancing Script',cursive;
    font-weight:700;
    font-size:clamp(30px,6.6vw,52px);
    margin:8px 0 0;
    color:#e0277f;
    line-height:1.12;
    text-shadow:0 2px 0 #fff, 0 10px 22px rgba(224,39,127,.28);
  }
  .nick{
    display:inline-block;margin-top:6px;
    font-family:'Dancing Script',cursive;
    font-size:23px;color:#b8336b;
  }
  .divider{
    margin:16px 0 6px;
    font-size:15px;letter-spacing:2px;
    color:#ff7ab8;
    opacity:.9;
  }
  .line{
    font-family:'Dancing Script',cursive;
    font-weight:700;
    color:#a8295f;
    margin:12px 0;
    line-height:1.35;
    opacity:0;
    animation:rise .9s cubic-bezier(.2,.8,.3,1) forwards;
  }
  .l1{font-size:clamp(24px,5.6vw,36px); animation-delay:.45s;}
  .l2{font-size:clamp(22px,5.1vw,33px); animation-delay:.95s;}
  .l3{font-size:clamp(25px,5.8vw,39px); color:#d81b60; animation-delay:1.45s;}
  .l4{font-size:clamp(20px,4.6vw,31px); animation-delay:1.95s;}
  @keyframes rise{
    from{opacity:0;transform:translateY(16px) scale(.97);}
    to  {opacity:1;transform:none;}
  }

  .forgive{
    margin-top:24px;
    font-family:'Poppins',sans-serif;
    font-weight:600;font-size:17px;
    padding:15px 38px;
    border:none;border-radius:999px;cursor:pointer;
    color:#fff;
    background:linear-gradient(135deg,#ff7ab8,#ff2d85);
    box-shadow:0 12px 26px rgba(255,45,133,.45), inset 0 -3px 0 rgba(0,0,0,.13);
    transition:transform .16s ease, box-shadow .16s ease, filter .16s ease;
    animation:rise .9s cubic-bezier(.2,.8,.3,1) 2.4s forwards;
    opacity:0;
  }
  .forgive:hover{transform:translateY(-3px) scale(1.04);box-shadow:0 16px 32px rgba(255,45,133,.55);}
  .forgive:active{transform:scale(.96);}

  .after{
    margin-top:18px;
    font-family:'Dancing Script',cursive;
    font-size:24px;color:#d81b60;
    min-height:32px;
  }

  /* burst hearts */
  .pop{position:fixed;z-index:999;pointer-events:none;will-change:transform,opacity;}

  /* ---------- responsive ---------- */
  @media (max-width:560px){
    .bouquet-wrap{height:340px;width:min(430px,94vw);}
    .bouquet{transform:scale(.76);transform-origin:50% 100%;}
    .glow{width:400px;height:400px;margin:-200px 0 0 -200px;}
    .letter{margin-top:-45px;padding:26px 18px 26px;border-radius:26px;}
    .bow{transform:scale(.9);transform-origin:50% 100%;}
  }
</style>
</head>
<body>

<div class="bg-hearts" id="bgHearts"></div>

<main>
  <!-- ===== BOUQUET ===== -->
  <div class="bouquet-wrap">
    <div class="sway">
      <div class="glow"></div>
      <div class="bouquet" id="bouquet">
        <div class="wrap"></div>
        <div class="bow">
          <span class="loop left"></span>
          <span class="loop right"></span>
          <span class="knot"></span>
          <span class="tail t1"></span>
          <span class="tail t2"></span>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== LETTER ===== -->
  <div class="letter">
    <div class="to">To my dearest</div>
    <h1>HANSANI&nbsp;NAYANATHARA</h1>
    <span class="nick">( my Alee 💗 )</span>

    <div class="divider">🌸 ─── 💗 ─── 🌸</div>

    <p class="line l1">Pretty Little Baby 🥺💗</p>
    <p class="line l2">Good HUNZZ Baby 🥺💗</p>
    <p class="line l3">Forgive me.... 💔😢</p>
    <p class="line l4">I will control my walkama.... 😔💗</p>

    <button class="forgive" id="forgiveBtn">Forgive Me 🥺💗</button>
    <div class="after" id="afterMsg"></div>
  </div>
</main>

<script>
/* ================= FLOATING BACKGROUND HEARTS ================= */
(function(){
  const wrap = document.getElementById('bgHearts');
  const emojis = ['💗','💖','💕','🌸','✨','🎀','💞','🌷','🩷'];
  for (let i = 0; i < 28; i++){
    const h = document.createElement('span');
    h.className = 'heart';
    h.textContent = emojis[Math.floor(Math.random() * emojis.length)];
    h.style.left = (Math.random() * 100) + 'vw';
    h.style.fontSize = (14 + Math.random() * 24) + 'px';
    h.style.animationDuration = (10 + Math.random() * 13) + 's';
    h.style.animationDelay = (-Math.random() * 22) + 's';
    h.style.setProperty('--o', (0.35 + Math.random() * 0.5).toFixed(2));
    wrap.appendChild(h);
  }
})();

/* ================= BUILD THE BOUQUET ================= */
(function(){
  const bouquet = document.getElementById('bouquet');

  // flowers: x / y offsets (y is negative = upward), size, colour, tilt
  const flowers = [
    { x:   0, y:-335, s:1.15, c:'#ff7ab8', r:  0 },
    { x: -98, y:-300, s:0.95, c:'#ffa8d4', r:-12 },
    { x:  98, y:-300, s:0.95, c:'#ff9ecb', r: 12 },
    { x:-168, y:-235, s:1.05, c:'#ffc2e0', r:-20 },
    { x: 168, y:-235, s:1.05, c:'#ffb3d9', r: 20 },
    { x: -58, y:-218, s:0.80, c:'#ffffff', r: -8 },
    { x:  58, y:-218, s:0.80, c:'#fff0f7', r:  8 },
    { x:-122, y:-158, s:0.70, c:'#e9a8ff', r:-16 },
    { x: 122, y:-158, s:0.70, c:'#f3b6ff', r: 16 },
    { x:   0, y:-215, s:0.85, c:'#ffd1e8', r:  0 }
  ];

  // stems first (behind everything)
  flowers.forEach(f => {
    const stem = document.createElement('span');
    stem.className = 'stem';
    const len = Math.hypot(f.x, f.y);
    const ang = Math.atan2(f.x, -f.y) * 180 / Math.PI;
    stem.style.height = len + 'px';
    stem.style.transform = 'rotate(' + ang + 'deg)';
    bouquet.appendChild(stem);
  });

  // leaves
  const leaves = [
    { x:-195, y:-195, r:-42, s:1.00 },
    { x: 195, y:-195, r: 42, s:1.00 },
    { x:-152, y:-122, r:-26, s:0.85 },
    { x: 152, y:-122, r: 26, s:0.85 },
    { x: -62, y:-105, r:-72, s:0.65 },
    { x:  62, y:-105, r: 72, s:0.65 }
  ];
  leaves.forEach(l => {
    const el = document.createElement('span');
    el.className = 'leaf';
    el.style.transform =
      'translate(calc(-50% + ' + l.x + 'px), ' + l.y + 'px) rotate(' + l.r + 'deg) scale(' + l.s + ')';
    bouquet.appendChild(el);
  });

  // flowers
  flowers.forEach(f => {
    const el = document.createElement('div');
    el.className = 'flower';
    el.style.setProperty('--x', f.x + 'px');
    el.style.setProperty('--y', f.y + 'px');
    el.style.setProperty('--s', f.s);
    el.style.setProperty('--r', (f.r || 0) + 'deg');
    el.style.setProperty('--c', f.c);

    for (let i = 0; i < 8; i++){
      const p = document.createElement('span');
      p.className = 'petal';
      p.style.setProperty('--i', i);
      el.appendChild(p);
    }
    const core = document.createElement('span');
    core.className = 'core';
    el.appendChild(core);

    bouquet.appendChild(el);
  });
})();

/* ================= FORGIVE BUTTON → HEART EXPLOSION ================= */
(function(){
  const btn = document.getElementById('forgiveBtn');
  const after = document.getElementById('afterMsg');
  const emojis = ['💗','💖','💕','🌸','✨','🎀','💞','🩷','🥺'];
  const messages = [
    'Thank you my Alee 💗😘',
    'You are my whole world 🌸💗',
    'I promise, no more walkama 😔💗',
    'I love you HANSANI 💖'
  ];

  btn.addEventListener('click', () => {
    const r = btn.getBoundingClientRect();
    const cx = r.left + r.width / 2;
    const cy = r.top + r.height / 2;

    for (let i = 0; i < 34; i++){
      const s = document.createElement('span');
      s.className = 'pop';
      s.textContent = emojis[Math.floor(Math.random() * emojis.length)];
      s.style.left = cx + 'px';
      s.style.top = cy + 'px';
      s.style.fontSize = (16 + Math.random() * 24) + 'px';
      document.body.appendChild(s);

      const dx = (Math.random() - 0.5) * 460;
      const dy = -(140 + Math.random() * 420);
      const rot = (Math.random() - 0.5) * 420;

      s.animate([
        { transform: 'translate(-50%,-50%) scale(.35) rotate(0deg)', opacity: 1 },
        { transform: 'translate(calc(-50% + ' + dx + 'px), calc(-50% + ' + dy + 'px)) scale(1.25) rotate(' + rot + 'deg)', opacity: 0 }
      ], {
        duration: 1200 + Math.random() * 950,
        easing: 'cubic-bezier(.2,.7,.3,1)'
      }).onfinish = () => s.remove();
    }

    btn.textContent = 'Thank you my Alee 💗😘';
    after.textContent = messages[Math.floor(Math.random() * messages.length)];
  });
})();
</script>
</body>
</html>
