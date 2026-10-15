```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#080808">
<meta name="description" content="MD4SHIELD — Next-generation FiveM server security.">
<title>MD4SHIELD | FiveM Security</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@500;600;700;800&family=Inter:wght@400;500;600;700;800&display=swap');

:root{--red:#ff1838;--red2:#a90020;--bg:#070809;--panel:#0e1014;--line:#24262e;--muted:#9da3b1;--white:#f5f6fa}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;scroll-padding-top:90px}
body{background:var(--bg);color:var(--white);font-family:Inter,Arial,sans-serif;line-height:1.6;overflow-x:hidden}
a{color:inherit;text-decoration:none}
button{font:inherit;cursor:pointer}
.container{width:min(1120px,91%);margin:auto}
header{position:sticky;top:0;z-index:50;background:#08090bea;backdrop-filter:blur(18px);border-bottom:1px solid #ffffff12}
.nav{height:76px;display:flex;align-items:center;justify-content:space-between;gap:20px}
.brand{display:flex;align-items:center;gap:11px;font-family:Orbitron,sans-serif;font-size:20px;font-weight:800;letter-spacing:-1px}
.brand span{color:var(--red)}
.logo{width:39px;height:43px;filter:drop-shadow(0 0 8px #ff183855)}
.links{display:flex;gap:28px;align-items:center;color:#c2c5ce;font-size:13px}
.links a:hover{color:var(--red)}
.btn{display:inline-flex;align-items:center;justify-content:center;gap:9px;padding:13px 20px;border-radius:9px;border:1px solid var(--red);font-weight:700;font-size:13px;transition:.2s}
.btn-red{background:var(--red);color:white;box-shadow:0 0 24px #ff183824}
.btn-red:hover{background:#db0928;transform:translateY(-2px)}
.btn-outline{background:#ffffff05;border-color:#41434d}
.btn-outline:hover{border-color:var(--red)}
.menu{display:none;background:none;border:0;color:white;font-size:25px}
.hero{position:relative;isolation:isolate;min-height:565px;display:flex;align-items:center;overflow:hidden;border-bottom:1px solid #ff183825}
.hero:before{content:"";position:absolute;inset:0;z-index:-2;background:radial-gradient(ellipse at 77% 45%,#8f001f42,transparent 36%),linear-gradient(100deg,#08090a 30%,#11070b 72%,#08090a)}
.hero:after{content:"";position:absolute;right:-100px;top:50px;width:520px;height:520px;border:1px solid #ff18382b;transform:rotate(35deg);box-shadow:0 0 100px #ff18380c,inset 0 0 80px #ff18380b;z-index:-1}
.hero-grid{display:grid;grid-template-columns:1.1fr .9fr;align-items:center;gap:30px;padding-top:65px;padding-bottom:65px}
.eyebrow{display:inline-block;color:#ff657a;border:1px solid #ff18385c;background:#ff18380d;padding:6px 11px;border-radius:4px;font-size:10px;font-weight:800;letter-spacing:2px;text-transform:uppercase}
h1{font-family:Orbitron,sans-serif;font-size:clamp(38px,5.1vw,65px);line-height:1.12;letter-spacing:-2.5px;margin:22px 0}
h1 span,.red{color:var(--red)}
.hero p{max-width:520px;color:#aeb3bf;font-size:15px;line-height:1.9}
.actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:28px}
.trust{display:flex;gap:20px;flex-wrap:wrap;margin-top:30px;color:#a6acb9;font-size:11px}
.trust b{color:var(--red);margin-right:6px}
.visual{position:relative;min-height:370px;display:grid;place-items:center}
.shield{width:min(300px,75%);aspect-ratio:1;display:grid;place-items:center;clip-path:polygon(50% 0,91% 17%,84% 69%,50% 100%,16% 69%,9% 17%);background:linear-gradient(140deg,#ff2847,#42000e 42%,#101115 72%,#e10b2d);filter:drop-shadow(0 0 45px #ff18383c);padding:3px}
.shield-inner{width:100%;height:100%;clip-path:polygon(50% 0,91% 17%,84% 69%,50% 100%,16% 69%,9% 17%);background:radial-gradient(circle at 50% 40%,#330710,#090a0d 66%);display:grid;place-items:center}
.shield-inner svg{width:46%;filter:drop-shadow(0 0 16px #ff1838)}
.visual-label{position:absolute;bottom:10px;right:0;color:#ff6c80;font-family:Orbitron,sans-serif;font-size:10px;letter-spacing:3px}
section{padding:88px 0}
.section-head{text-align:center;max-width:650px;margin:0 auto 38px}
.kicker{color:var(--red);font-size:11px;font-weight:800;letter-spacing:3px;text-transform:uppercase}
h2{font-family:Orbitron,sans-serif;font-size:clamp(25px,3vw,37px);line-height:1.3;margin:12px 0}
.section-head p,.muted{color:var(--muted);font-size:14px}
.features{display:grid;grid-template-columns:repeat(3,1fr);gap:15px}
.card{background:linear-gradient(145deg,#111319,#0a0b0e);border:1px solid var(--line);border-radius:13px;padding:25px;transition:.25s}
.card:hover{border-color:#ff18387a;transform:translateY(-4px);box-shadow:0 15px 40px #0005}
.feature-icon{width:45px;height:45px;border-radius:10px;border:1px solid #ff18384f;background:#ff183811;display:grid;place-items:center;color:var(--red);font-size:21px;margin-bottom:20px}
.card h3{font-size:16px;margin-bottom:9px}
.card p{font-size:13px;color:var(--muted);line-height:1.8}
.pricing-section{background:radial-gradient(ellipse at 50% 0,#3c06111f,transparent 55%),#090a0d;border-top:1px solid #ffffff0d;border-bottom:1px solid #ffffff0d}
.pricing{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;align-items:stretch}
.price-card{position:relative}
.price-card.popular{border-color:var(--red);box-shadow:0 0 35px #ff183814}
.popular-label{position:absolute;top:-12px;left:22px;background:var(--red);padding:4px 10px;border-radius:4px;font-size:9px;font-weight:800;letter-spacing:1px}
.plan{font-size:11px;color:#c2c6d0;letter-spacing:2px;font-weight:800}
.price{font-family:Orbitron,sans-serif;font-size:38px;font-weight:800;margin:15px 0 4px}
.price small{font-family:Inter,sans-serif;font-size:12px;color:var(--muted);font-weight:500}
ul{list-style:none;margin:23px 0}
li{font-size:13px;color:#c7cad2;margin:12px 0}
li:before{content:"✓";color:var(--red);font-weight:900;margin-right:10px}
.price-card .btn{width:100%}
.notice{font-size:11px;color:#818795;text-align:center;margin-top:22px}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:50px;align-items:center}
.about-panel{border:1px solid var(--line);background:linear-gradient(140deg,#171017,#0c0d10);padding:30px;border-radius:14px}
.stat-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.stat{padding:19px;background:#ffffff04;border:1px solid #ffffff12;border-radius:9px}
.stat strong{font-family:Orbitron,sans-serif;color:var(--red);font-size:25px;display:block}
.stat span{font-size:11px;color:var(--muted)}
.about-copy p{color:var(--muted);font-size:14px;line-height:1.9;margin:15px 0}
.faq{max-width:800px;margin:auto}
details{background:#0d0f13;border:1px solid var(--line);border-radius:9px;padding:19px 21px;margin:10px 0}
summary{cursor:pointer;font-size:14px;font-weight:700}
details p{color:var(--muted);font-size:13px;padding-top:14px;line-height:1.8}
footer{border-top:1px solid #ffffff12;padding:30px 0}
.footer-row{display:flex;justify-content:space-between;align-items:center;gap:20px;flex-wrap:wrap}
footer p{color:#777e8d;font-size:11px}
footer .links{gap:17px;flex-wrap:wrap}
@media(max-width:800px){.links{gap:14px}.hero-grid{grid-template-columns:1fr}.hero{min-height:auto}.visual{min-height:280px}.shield{width:220px}.features{grid-template-columns:repeat(2,1fr)}.about-grid{grid-template-columns:1fr;gap:25px}}
@media(max-width:600px){.nav{height:66px}.brand{font-size:16px}.brand .logo{width:32px}.menu{display:block}.links{display:none;position:absolute;top:66px;left:0;right:0;padding:22px 5%;background:#0b0c10;border-bottom:1px solid var(--line);flex-direction:column;align-items:flex-start}.links.open{display:flex}.nav>.btn{padding:10px;font-size:11px}.hero-grid{padding-top:50px;padding-bottom:45px}h1{letter-spacing:-1.5px}.trust{gap:12px}.features,.pricing{grid-template-columns:1fr}section{padding:65px 0}.card{padding:22px}.visual{min-height:250px}.footer-row{align-items:flex-start;flex-direction:column}}
</style>
</head>
<body>
<header>
 <div class="container nav">
  <a class="brand" href="#home">
   <svg class="logo" viewBox="0 0 60 65" fill="none" aria-label="MD4SHIELD logo"><path d="M30 3 53 15 49 43 30 61 11 43 7 15Z" stroke="#ff1838" stroke-width="3"/><path d="M30 12 45 20 42 39 30 50 18 39 15 20Z" stroke="#ff1838" stroke-width="2"/><path d="M18 24 27 34 27 22 33 22 33 34 42 24 39 40 30 47 21 40Z" fill="#ff1838"/></svg>
   MD<span>4SHIELD</span>
  </a>
  <nav class="links" id="navlinks">
   <a href="#home">Home</a><a href="#features">Features</a><a href="#pricing">Pricing</a><a href="#about">About</a><a href="#faq">FAQ</a>
  </nav>
  <a class="btn btn-outline" href="#pricing">Get Protected ↗</a>
  <button class="menu" id="menu" aria-label="Open menu">☰</button>
 </div>
</header>
<main>
<section class="hero" id="home">
 <div class="container hero-grid">
  <div>
   <span class="eyebrow">Next-generation FiveM security</span>
   <h1>PROTECT YOUR<br><span>FIVEM SERVER.</span></h1>
   <p>Take your server security to the next level with MD4SHIELD. A bold security brand built for FiveM communities that value protection, control, and reliability.</p>
   <div class="actions"><a class="btn btn-red" href="#pricing">Explore Plans <span>→</span></a><a class="btn btn-outline" href="#features">Discover Features</a></div>
   <div class="trust"><span><b>◆</b> Security-focused</span><span><b>◆</b> Modern dashboard concept</span><span><b>◆</b> Built for FiveM</span></div>
  </div>
  <div class="visual">
   <div class="shield"><div class="shield-inner"><svg viewBox="0 0 100 110" fill="none"><path d="M50 5 88 24 81 70 50 101 19 70 12 24Z" stroke="#ff1838" stroke-width="4"/><path d="M25 35 43 55 43 35 57 35 57 55 75 35 68 67 50 81 32 67Z" fill="#ff1838"/></svg></div></div>
   <div class="visual-label">MD4SHIELD / SECURITY</div>
  </div>
 </div>
</section>
<section id="features">
 <div class="container">
  <div class="section-head"><div class="kicker">Built for protection</div><h2>Security. Without compromise.</h2><p>A clean overview of the tools and services your FiveM community may need.</p></div>
  <div class="features">
   <article class="card"><div class="feature-icon">⬡</div><h3>Anti-Cheat Protection</h3><p>A security-focused service concept designed to help keep gameplay fair.</p></article>
   <article class="card"><div class="feature-icon">⊘</div><h3>Ban Management</h3><p>Keep moderation organized with a clear ban-management workflow concept.</p></article>
   <article class="card"><div class="feature-icon">▤</div><h3>Security Logs</h3><p>Present security events and activity in an easy-to-read format.</p></article>
   <article class="card"><div class="feature-icon">⌘</div><h3>API Integration</h3><p>A place to describe integrations supported by your actual service.</p></article>
   <article class="card"><div class="feature-icon">▦</div><h3>Client Dashboard</h3><p>A planned central place for customers to manage their service.</p></article>
   <article class="card"><div class="feature-icon">◉</div><h3>Customer Support</h3><p>Give customers a clear route to your official support community.</p></article>
  </div>
 </div>
</section>
<section class="pricing-section" id="pricing">
 <div class="container">
  <div class="section-head"><div class="kicker">Simple plans</div><h2>Choose your protection.</h2><p>Pick the plan that matches your server. Confirm the final prices and included features before accepting payments.</p></div>
  <div class="pricing">
   <article class="card price-card"><div class="plan">MONTHLY</div><div class="price">€50 <small>/ month</small></div><p class="muted">Flexible monthly access.</p><ul><li>Service access as agreed</li><li>Updates as specified</li><li>Support via Discord</li></ul><a class="btn btn-outline" href="#contact">Choose Monthly</a></article>
   <article class="card price-card popular"><div class="popular-label">POPULAR PLAN</div><div class="plan">QUARTERLY</div><div class="price">€100 <small>/ 3 months</small></div><p class="muted">A longer plan for your server.</p><ul><li>Three-month access</li><li>Updates as specified</li><li>Support via Discord</li></ul><a class="btn btn-red" href="#contact">Choose Quarterly</a></article>
   <article class="card price-card"><div class="plan">LIFETIME</div><div class="price">€250 <small>/ one-time</small></div><p class="muted">One-time payment option.</p><ul><li>Lifetime terms must be defined</li><li>Updates as specified</li><li>Support via Discord</li></ul><a class="btn btn-outline" href="#contact">Choose Lifetime</a></article>
  </div>
  <p class="notice">Demo pricing only. These buttons do not process payments. Final terms, delivery and support must be configured by the owner.</p>
 </div>
</section>
<section id="about">
 <div class="container about-grid">
  <div class="about-copy"><div class="kicker">Why MD4SHIELD</div><h2>A stronger identity for your server security.</h2><p>MD4SHIELD combines a sharp black-and-red identity with a straightforward customer experience. Explain exactly what your product does, what each plan includes, and how customers can get help.</p><p>Trust comes from transparent terms, real product documentation, and reliable support—not just a strong design.</p><a class="btn btn-red" href="#contact">Contact the Team →</a></div>
  <div class="about-panel"><div class="stat-grid"><div class="stat"><strong>24/7</strong><span>Support availability — set your real hours</span></div><div class="stat"><strong>FIVEM</strong><span>Focused community</span></div><div class="stat"><strong>SECURE</strong><span>Security-first design</span></div><div class="stat"><strong>MD4</strong><span>One recognizable brand</span></div></div></div>
 </div>
</section>
<section id="faq">
 <div class="container">
  <div class="section-head"><div class="kicker">Need to know</div><h2>Frequently asked questions.</h2></div>
  <div class="faq">
   <details><summary>Does this website already include a working anti-cheat?</summary><p>No. This is the website frontend only. A real anti-cheat, API, authentication, and customer dashboard require separate backend development and testing.</p></details>
   <details><summary>Does Discord Login work?</summary><p>Not yet. Discord OAuth needs a registered Discord application, a secure backend, and configured redirect URLs. Never put a client secret in this HTML file.</p></details>
   <details><summary>Can I change prices and plan details?</summary><p>Yes. Find the PRICING section in this file and edit the displayed amounts and features to match your real offer.</p></details>
   <details><summary>How can customers contact me?</summary><p>Add your real Discord invite or support URL to the contact links below before publishing.</p></details>
  </div>
 </div>
</section>
<section id="contact">
 <div class="container">
  <div class="section-head"><div class="kicker">Get in touch</div><h2>Ready to secure your community?</h2><p>Connect this button to your real Discord server or contact page.</p>
   <div class="actions" style="justify-content:center"div><a class="btn btn-red"
   href="https://discord.gg/https://https://https://discord.gg/6p85F5pQ5"
   target="_blank"
   rel="noopener noreferrer">
   <img src="https://cdn.simpleicons.org/discord/FFFFFF"
        alt="Discord"
        width="18"
        height="18">
   Join Discord →
</a>
  </div>
 </div>
</section>
</main>
<footer><div class="container footer-row"><a class="brand" href="#home">MD<span>4SHIELD</span></a><div class="links"><a href="#features">Features</a><a href="#pricing">Pricing</a><a href="#faq">FAQ</a></div><p>© 2026 MD4SHIELD. All rights reserved.</p></div></footer>
<script>
const menu=document.getElementById('menu');
const nav=document.getElementById('navlinks');
menu.addEventListener('click',()=>{nav.classList.toggle('open');menu.textContent=nav.classList.contains('open')?'✕':'☰'});
nav.querySelectorAll('a').forEach(a=>a.addEventListener('click',()=>{nav.classList.remove('open');menu.textContent='☰'}));
</script>
</body>
</html>
```
