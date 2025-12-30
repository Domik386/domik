<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Domik — Артем</title>

<style>
:root{
  --accent:#ff8c1a;
  --accent2:#ff4d00;
  --bg:#050505;
  --glass:rgba(18,18,18,.62);
  --glass2:rgba(18,18,18,.78);
  --border:rgba(255,255,255,.10);
  --muted:#a9a9a9;
  --text:#fff;
  --shadow: 0 20px 60px rgba(0,0,0,.55);
  --glow: 0 0 30px rgba(255,140,26,.35);
}

*{box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  margin:0;
  font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
  color:var(--text);
  background: var(--bg);
  overflow-x:hidden;
}

/* Cursor glow */
.cursor-glow{
  position:fixed;
  width:520px;height:520px;
  border-radius:50%;
  background: radial-gradient(circle, rgba(255,140,26,.20), transparent 60%);
  pointer-events:none;
  z-index:-1;
  transform: translate(-50%, -50%);
  mix-blend-mode: screen;
}

/* HEADER */
header{
  position:sticky;
  top:0;
  z-index:30;
  backdrop-filter: blur(14px);
  background: rgba(7,7,7,.55);
  border-bottom: 1px solid rgba(255,255,255,.08);
}
.topbar{
  max-width:1180px;
  margin:auto;
  padding:18px 18px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:14px;
}
.brand{
  display:flex;
  align-items:center;
  gap:10px;
  font-weight:900;
  letter-spacing:.3px;
  user-select:none;
}
.badge{
  width:40px;height:40px;
  border-radius:14px;
  background: linear-gradient(135deg, var(--accent), var(--accent2));
  box-shadow: var(--glow);
  display:grid;
  place-items:center;
  color:#070707;
  font-weight:1000;
}
.brand span{
  font-size:20px;
  background: linear-gradient(135deg, var(--accent), var(--accent2));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}
nav{
  display:flex;
  gap:18px;
  align-items:center;
}
nav a{
  color:var(--muted);
  text-decoration:none;
  font-size:14px;
  padding:8px 8px;
  border-radius:10px;
}
nav a:hover{ color:#fff; background:rgba(255,255,255,.06); }

/* MOBILE MENU */
.burger{
  display:none;
  width:44px;height:44px;
  border-radius:14px;
  border:1px solid rgba(255,255,255,.12);
  background: rgba(255,255,255,.05);
  cursor:pointer;
}
.burger span{
  display:block;
  width:18px;height:2px;
  background:#fff;
  margin:5px auto;
  border-radius:2px;
}
.mobile-nav{
  display:none;
  padding:10px 18px 18px;
  max-width:1180px;
  margin:auto;
}
.mobile-nav a{
  display:block;
  padding:12px 12px;
  margin-top:10px;
  border:1px solid rgba(255,255,255,.10);
  background: rgba(255,255,255,.04);
  border-radius:14px;
  color:#fff;
  text-decoration:none;
}

/* LAYOUT */
.container{
  max-width:1180px;
  margin:auto;
  padding:26px 18px 0;
}
section{ margin-top:84px; animation:fadeUp .8s ease both; }
@keyframes fadeUp{
  from{opacity:0;transform:translateY(30px);}
  to{opacity:1;transform:translateY(0);}
}
h2{
  font-size:30px;
  margin-bottom:26px;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

/* STATS LINKS */
.stat a{
  color: var(--muted);
  text-decoration: none;
  font-size:13px;
  word-break: break-all;
}
.stat a:hover{ color:#ff8c1a; }

/* CARDS */
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(260px,1fr));
  gap:18px;
}
.card{
  background:var(--glass);
  border:1px solid var(--border);
  border-radius:22px;
  padding:18px;
  backdrop-filter:blur(14px);
  transition:.28s;
  position:relative;
  overflow:hidden;
}
.card:hover{
  transform:translateY(-6px);
  border-color:var(--accent);
  box-shadow:var(--glow);
}
.card h4{ margin:0 0 8px;font-size:16px; }
.card p{ margin:0;font-size:13px;color:var(--muted); }

/* COPY BLOCK */
.card.copy{ cursor:pointer; }
.card.copy small{
  display:block;
  color:#7f7f7f;
  margin-top:10px;
  font-size:11px;
}

/* CONTACTS */
.contact{
  display:flex;
  gap:12px;
  align-items:center;
}
.icon{
  width:48px;height:48px;
  border-radius:16px;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  display:grid;place-items:center;
  color:#0b0b0b;font-weight:1000;
}

/* FOOTER */
footer{
  margin-top:90px;
  padding:44px 18px;
  text-align:center;
  color:#6f6f6f;
  font-size:13px;
  border-top:1px solid rgba(255,255,255,.06);
  background:rgba(0,0,0,.25);
}

/* HERO */
.hero{
  margin-top:28px;
  display:grid;
  grid-template-columns:1.25fr .75fr;
  gap:22px;
}
.hero-card{
  background:var(--glass2);
  border:1px solid var(--border);
  border-radius:24px;
  padding:28px;
  backdrop-filter:blur(16px);
  box-shadow:var(--shadow);
}
.hero-card h1{
  margin:14px 0 10px;
  font-size:44px;
  line-height:1.05;
}
.hero-card p{ line-height:1.8;color:#d8d8d8;font-size:15px; }
.hero-actions{
  margin-top:18px;
  display:flex;flex-wrap:wrap;
  gap:10px;
}
.btn{
  border:1px solid rgba(255,255,255,.10);
  background:rgba(255,255,255,.05);
  color:#fff;padding:10px 14px;
  border-radius:16px;font-size:14px;
  cursor:pointer;text-decoration:none;
  display:inline-flex;align-items:center;gap:8px;
  transition:.25s;
}
.btn.primary{
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  color:#000;border:0;font-weight:800;
}
.btn:hover{ transform:translateY(-2px);box-shadow:var(--glow); }

@media (max-width:920px){
  .hero{grid-template-columns:1fr;}
  header nav{display:none;}
  .burger{display:block;}
  .hero-card h1{font-size:38px;}
}
</style>
</head>

<body>

<div class="orbs">
  <div class="orb"></div>
  <div class="orb"></div>
  <div class="orb"></div>
</div>
<div class="cursor-glow" id="glow"></div>

<header>
  <div class="topbar">
    <div class="brand">
      <div class="badge">D</div>
      <span>Domik</span>
    </div>

    <nav>
      <a href="#about">Обо мне</a>
      <a href="#support">Поддержка</a>
      <a href="#system">Система</a>
      <a href="#contacts">Контакты</a>
    </nav>

    <div class="actions">
      <a class="btn" href="#support">💸 Донат</a>
      <a class="btn primary" href="https://t.me/domikteam1" target="_blank" rel="noreferrer">📣 Telegram</a>
      <button class="burger" id="burger" aria-label="Открыть меню">
        <span></span><span></span><span></span>
      </button>
    </div>
  </div>

  <div class="mobile-nav" id="mobileNav">
    <a href="#about">Обо мне</a>
    <a href="#support">Поддержка</a>
    <a href="#system">Система</a>
    <a href="#contacts">Контакты</a>
  </div>
</header>

<div class="container">

<div class="hero">
  <div class="hero-card" id="about">
    <h1>Артем <span>aka</span> <span style="color:#ff8c1a">Domik</span></h1>
    <p>
      Привет! Меня зовут Артем, в сети я известен как <b>Domik</b>.
      Провожу стримы, играю в CS2, много общаюсь с чатом и создаю ламповую атмосферу.
      <br><br>
      Здесь ты можешь узнать больше обо мне, поддержать стрим или связаться напрямую.
      Спасибо, что ты здесь 🧡
    </p>
  </div>

  <div class="hero-card">
    <div class="stat"><b>Подписчики</b><span>1 337</span></div>
    <div class="stat"><b>Стримов в этом году</b><span>96</span></div>
    <div class="stat"><b>Любимая игра</b><span>CS2</span></div>
  </div>
</div>

<section id="support">
  <h2>Поддержать меня</h2>
  <div class="grid">
    <div class="card copy" data-copy="DWQSsLZ1JYty7LHe2f11FKGFpx9bGenQ1SAqdGpPFUFX">
      <h4>Solana</h4>
      <p>Нажми чтобы скопировать</p>
    </div>
    <div class="card copy" data-copy="bc1qkztctt0m825q0y0alqfhagvg2mqh6uwwhfgdah">
      <h4>Bitcoin (BTC)</h4>
      <p>Нажми чтобы скопировать</p>
    </div>
    <div class="card copy" data-copy="https://t.me/+YrEYNQy0OBYzYzg0">
      <h4>Telegram Chat</h4>
      <p>Нажми чтобы скопировать ссылку</p>
    </div>
    <a class="card" href="https://donatepay.ru/don/1451218" target="_blank" rel="noreferrer">
      <h4>DonatePay</h4>
      <p>Клик = перейти</p>
    </a>
    <a class="card" href="https://www.donationalerts.com/r/domik122" target="_blank" rel="noreferrer">
      <h4>DonationAlerts</h4>
      <p>Клик = перейти</p>
    </a>
  </div>
</section>

<section id="system">
  <h2>Система стрима</h2>
  <div class="grid">
    <div class="card"><h4>CPU</h4><p>Intel Core i7-14700F</p></div>
    <div class="card"><h4>GPU</h4><p>NVIDIA RTX 4070 SUPER</p></div>
    <div class="card"><h4>RAM</h4><p>32 GB DDR5</p></div>
    <div class="card"><h4>SSD</h4><p>Samsung 990 PRO 1TB</p></div>
  </div>
</section>

<section id="contacts">
  <h2>Контакты</h2>
  <div class="grid">
    <a class="card" href="https://t.me/domikteam1" target="_blank" rel="noreferrer">
      <div class="contact"><div class="icon">TG</div><div><h4>Telegram</h4><p>@domikteam1</p></div></div>
    </a>
    <a class="card" href="https://t.me/+YrEYNQy0OBYzYzg0" target="_blank" rel="noreferrer">
      <div class="contact"><div class="icon">💬</div><div><h4>Чат</h4><p>t.me/+YrEYNQ…</p></div></div>
    </a>
    <a class="card" href="https://www.tiktok.com/@domikteam" target="_blank" rel="noreferrer">
      <div class="contact"><div class="icon">TT</div><div><h4>TikTok</h4><p>@domikteam</p></div></div>
    </a>
  </div>
</section>

</div>

<footer>© Артем (Domik) • 2025</footer>

<script>
// burger
document.getElementById('burger')?.addEventListener('click', () => {
  document.getElementById('mobileNav').classList.toggle('open');
});
window.addEventListener('mousemove', e => {
  glow.style.left = e.clientX + 'px';
  glow.style.top  = e.clientY + 'px';
});
document.querySelectorAll('.card.copy').forEach(card => {
  card.addEventListener('click', () => copyText(card.dataset.copy));
});
function showToast(msg){
  const t=document.getElementById('toast');
  const tt=document.getElementById('toastText');
  tt.textContent=msg;
  t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),1400);
}
async function copyText(text){
  if(!text) return;
  try{await navigator.clipboard.writeText(text);}catch{}
  showToast('Скопировано!');
}
</script>

<div class="toast" id="toast"><i>✓</i><span id="toastText">Скопировано!</span></div>

</body>
</html>
