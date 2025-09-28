# Te-iubesc-piticotu-meu
Multumesc ca faci parte din viata meaaa
<html lang="ro">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Pagină de dragoste</title>
  <style>
    :root{
      --pink:#ffd4e6;
      --rose:#ff6fa3;
      --deep:#ff3b7a;
      font-family: "Poppins", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }

    html,body{height:100%;}
    body{
      margin:0;
      background: linear-gradient(180deg, var(--pink) 0%, #ffe6f2 50%, #fff 100%);
      display:flex;
      align-items:center;
      justify-content:center;
      padding:24px;
      overflow:hidden;
    }

    .card{
      width:100%;
      max-width:900px;
      background: linear-gradient(135deg, rgba(255,255,255,0.9), rgba(255,255,255,0.75));
      border-radius:20px;
      box-shadow: 0 12px 40px rgba(255,90,150,0.18);
      padding:28px;
      position:relative;
      overflow:hidden;
      backdrop-filter: blur(6px) saturate(120%);
      z-index:2;
    }

    .message{
      text-align:center;
      padding:28px 20px;
    }
    h1{
      margin:6px 0 16px 0;
      font-size:22px;
      line-height:1.25;
      color:#6b1738;
    }
    p.lead{
      font-size:18px;
      line-height:1.55;
      color:#421427;
      margin:0 auto 18px auto;
      max-width:760px;
      font-weight:500;
    }
    p.love{
      font-size:20px;
      font-weight:700;
      color:var(--deep);
      margin-top:6px;
    }

    .signature{
      position:fixed;
      right:18px;
      bottom:12px;
      font-size:14px;
      color:#6b1738;
      background: rgba(255,255,255,0.6);
      padding:8px 12px;
      border-radius:12px;
      box-shadow:0 6px 18px rgba(200,80,140,0.12);
    }

    .hearts-layer{
      pointer-events:none;
      position:absolute;
      inset:0;
      z-index:1;
      overflow:hidden;
    }

    .heart{
      position:absolute;
      width:40px;
      height:40px;
      transform: rotate(-45deg) scale(0.9);
      opacity:0.95;
    }
    .heart:before, .heart:after{
      content:"";
      position:absolute;
      width:100%;
      height:100%;
      border-radius:50%;
      background:var(--deep);
      left:0;
      top:0;
    }
    .heart:before{ left:50%; }
    .heart:after{ top:-50%; }

    @keyframes fall {
      0%{ transform: translateY(-120px) rotate(-45deg) scale(0.6); opacity:0 }
      10%{ opacity:1 }
      100%{ transform: translateY(110vh) rotate(-25deg) scale(1); opacity:0.95 }
    }

    .animated-hearts{
      display:flex;
      justify-content:center;
      gap:20px;
      margin-top:20px;
    }
    .animated-hearts .small-heart{
      width:30px;
      height:30px;
      background:var(--deep);
      position:relative;
      transform:rotate(-45deg);
      animation: pulse 1.5s infinite;
    }
    .animated-hearts .small-heart:nth-child(2){ animation-delay:0.5s; }
    .animated-hearts .small-heart:nth-child(3){ animation-delay:1s; }
    .animated-hearts .small-heart:before,
    .animated-hearts .small-heart:after{
      content:"";
      position:absolute;
      width:30px;
      height:30px;
      background:var(--deep);
      border-radius:50%;
    }
    .animated-hearts .small-heart:before{ top:-15px; left:0; }
    .animated-hearts .small-heart:after{ left:15px; top:0; }

    @keyframes pulse {
      0%,100%{ transform:rotate(-45deg) scale(1); }
      50%{ transform:rotate(-45deg) scale(1.3); }
    }

    @media (max-width:600px){
      h1{ font-size:18px }
      p.lead{ font-size:16px }
      p.love{ font-size:18px }
      .card{ padding:20px }
      .signature{ right:12px; bottom:10px; font-size:13px }
      .animated-hearts{ gap:14px }
      .animated-hearts .small-heart{ width:24px; height:24px }
      .animated-hearts .small-heart:before,
      .animated-hearts .small-heart:after{ width:24px; height:24px }
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="message">
      <h1>Multumesc ca ai grija de mine si ca ma faci mereu cel mai fericit baietel</h1>
      <p class="lead">"Sunt cel mai norocos băiețel pentru că am o iubită atât de perfectă, îi mulțumesc lui Dumnezeu că ai apărut în viața mea și că fiecare zi petrecută alături de tine e una de vis"</p>
      <p class="love">Te ador și te iubesc cel mai mult, piticotul meu 💖</p>
      <div class="animated-hearts">
        <div class="small-heart"></div>
        <div class="small-heart"></div>
        <div class="small-heart"></div>
      </div>
    </div>
    <div class="hearts-layer"></div>
  </div>

  <div class="signature">Cu drag, nebunu' tau</div>

  <!-- Embed YouTube pentru „Cel mai fericit de pe pământ” -->
  <div style="position:fixed; bottom:10px; left:10px; width:0; height:0; overflow:hidden; z-index:10;">
    <iframe width="1" height="1"
      src="https://www.youtube.com/embed/SM-N4pmi73A?autoplay=1&loop=1&playlist=SM-N4pmi73A"
      frameborder="0" allow="autoplay; encrypted-media" allowfullscreen>
    </iframe>
  </div>

  <script>
    const container = document.querySelector('.hearts-layer');
    const colors = ['#FFB3D9','#FF6FA3','#FF3B7A','#FFC6E0','#FF7FB0'];

    function rand(min,max){ return Math.random()*(max-min)+min }

    function createHeart(){
      const el = document.createElement('div');
      el.className = 'heart';
      const size = Math.round(rand(18,56));
      el.style.width = size+'px';
      el.style.height = size+'px';
      const left = Math.round(rand(2,98));
      el.style.left = left+'%';
      el.style.background = colors[Math.floor(Math.random()*colors.length)];
      el.style.top = '-10%';
      el.style.animation = `fall ${rand(6,12)}s linear forwards`;
      container.appendChild(el);
      setTimeout(()=>{ if(el && el.parentNode) el.parentNode.removeChild(el); }, 15000);
    }

    setInterval(createHeart, 800);
  </script>
</body>
</html>
