<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@400;500;600&display=swap');
  * { margin: 0; padding: 0; box-sizing: border-box; }
  :root { --black: #090909; --gold: #F5C842; --blue: #1A3A8F; --white: #F5F4F0; }
  body { background: var(--black); font-family: 'DM Sans', sans-serif; }

  nav {
    padding: 0 4rem; display: grid; grid-template-columns: 1fr auto 1fr;
    align-items: center; height: 84px; position: absolute; top: 0; left: 0; right: 0;
    z-index: 10; background: transparent;
    border-bottom: 1px solid rgba(245,200,66,0.2);
  }
  .nav-left { display: flex; gap: 3rem; align-items: center; justify-content: flex-end; }
  .nav-center { display: flex; flex-direction: column; align-items: center; gap: 2px; padding: 0 3rem; }
  .nav-right { display: flex; gap: 3rem; align-items: center; justify-content: flex-start; }
  .nav-left a, .nav-right a { color: var(--white); text-decoration: none; font-size: 16px; letter-spacing: 1.5px; text-transform: uppercase; opacity: 0.9; white-space: nowrap; }
  .nav-logo-img { width: 52px; height: 52px; object-fit: contain; }

  .hero { position: relative; min-height: 100vh; display: flex; align-items: center; overflow: hidden; }
  .hero-bg {
    position: absolute; inset: 0;
    background-image: url('IMG_7418.PNG');
    background-size: cover; background-position: center 25%; background-repeat: no-repeat;
    filter: brightness(0.65) saturate(0.75);
  }
  .hero-overlay { position: absolute; inset: 0; background: linear-gradient(90deg, rgba(9,9,9,0.92) 0%, rgba(9,9,9,0.6) 45%, rgba(9,9,9,0.1) 100%); }
  .hero-overlay-bottom { position: absolute; bottom: 0; left: 0; right: 0; height: 180px; background: linear-gradient(to top, rgba(9,9,9,1) 0%, transparent 100%); }

  .hero-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; width: 100%; padding: calc(84px + 4rem) 4rem 4rem; position: relative; z-index: 2; }

  .hero-badge { display: inline-flex; align-items: center; gap: 8px; background: rgba(245,200,66,0.08); border: 1px solid rgba(245,200,66,0.3); padding: 7px 16px; margin-bottom: 2rem; font-size: 10px; letter-spacing: 2.5px; text-transform: uppercase; color: var(--gold); }
  .dot { width: 5px; height: 5px; background: var(--gold); border-radius: 50%; animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }
  .hero-title { font-family: 'Bebas Neue', sans-serif; font-size: clamp(60px, 7vw, 110px); line-height: 0.92; color: var(--white); margin-bottom: 1.5rem; letter-spacing: 1px; }
  .gold { color: var(--gold); }
  .blue-outline { -webkit-text-stroke: 1px rgba(26,58,143,0.8); color: transparent; }
  .hero-sub { font-size: 16px; color: rgba(245,244,240,0.6); line-height: 1.7; margin-bottom: 2.5rem; max-width: 520px; }
  .hero-actions { display: flex; gap: 12px; margin-bottom: 3rem; }
  .btn-primary { background: var(--gold); color: var(--black); padding: 14px 30px; font-family: 'Bebas Neue', sans-serif; font-size: 15px; letter-spacing: 2px; border: none; cursor: pointer; }
  .btn-ghost { background: rgba(26,58,143,0.2); color: rgba(245,244,240,0.85); padding: 14px 24px; font-family: 'Bebas Neue', sans-serif; font-size: 15px; letter-spacing: 2px; border: 1px solid rgba(26,58,143,0.5); cursor: pointer; }
  .hero-stats { display: flex; gap: 2.5rem; padding-top: 2rem; border-top: 1px solid rgba(26,58,143,0.3); }
  .stat-num { font-family: 'Bebas Neue', sans-serif; font-size: 34px; color: var(--gold); line-height: 1; }
  .stat-label { font-size: 11px; color: rgba(245,244,240,0.4); letter-spacing: 1.5px; text-transform: uppercase; margin-top: 4px; }
  .hero-visual { display: flex; flex-direction: column; gap: 10px; }
  .visual-card { background: rgba(9,9,9,0.65); border: 1px solid rgba(245,200,66,0.12); padding: 1.1rem 1.4rem; display: flex; align-items: center; gap: 1rem; backdrop-filter: blur(10px); }
  .visual-card.featured { border-color: rgba(245,200,66,0.4); background: rgba(9,9,9,0.8); }
  .card-icon { font-size: 20px; width: 40px; text-align: center; flex-shrink: 0; }
  .card-name { font-family: 'Bebas Neue', sans-serif; font-size: 17px; color: var(--white); letter-spacing: 1px; }
  .card-detail { font-size: 11px; color: rgba(245,244,240,0.4); margin-top: 2px; }
  .card-price { margin-left: auto; font-family: 'Bebas Neue', sans-serif; font-size: 15px; color: var(--gold); flex-shrink: 0; }
  .card-badge { font-size: 9px; letter-spacing: 1.5px; text-transform: uppercase; background: rgba(245,200,66,0.08); color: rgba(245,200,66,0.7); padding: 3px 8px; margin-left: auto; border: 1px solid rgba(245,200,66,0.2); }
  .zone-tag { display: flex; align-items: center; gap: 8px; font-size: 10px; color: rgba(245,244,240,0.3); letter-spacing: 1px; text-transform: uppercase; margin-bottom: 2px; }
  .zone-line { flex: 1; height: 1px; background: rgba(245,200,66,0.1); }
</style>
</head>
<body>

<nav>
  <div class="nav-left">
    <a href="#">Services</a>
    <a href="#">Comment ça marche</a>
  </div>
  <div class="nav-center">
    <img src="logo.PNG" class="nav-logo-img" alt="Water Less logo" />
  </div>
  <div class="nav-right">
    <a href="#">Avis</a>
    <a href="#">Mon compte</a>
  </div>
</nav>

<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-overlay"></div>
  <div class="hero-overlay-bottom"></div>
  <div class="hero-inner">
    <div>
      <div class="hero-badge"><span class="dot"></span> Haute-Corse · À domicile</div>
      <h1 class="hero-title">DETAILING<br><span class="gold">SANS EAU.</span><br><span class="blue-outline">CHEZ TOI.</span></h1>
      <p class="hero-sub">On vient chez toi. On repart. Ta voiture, ta moto ou ton bateau ressort comme neuve — sans une goutte d'eau, sans que tu bouges.</p>
      <div class="hero-actions">
        <button class="btn-primary">PRENDRE RDV</button>
        <button class="btn-ghost">VOIR LES SERVICES</button>
      </div>
      <div class="hero-stats">
        <div><div class="stat-num">200+</div><div class="stat-label">Clients</div></div>
        <div><div class="stat-num">4.9★</div><div class="stat-label">Google</div></div>
        <div><div class="stat-num">0L</div><div class="stat-label">D'eau</div></div>
        <div><div class="stat-num">50%</div><div class="stat-label">Crédit impôt</div></div>
      </div>
    </div>
    <div class="hero-visual">
      <div class="zone-tag"><span>Nos prestations</span><span class="zone-line"></span></div>
      <div class="visual-card featured">
        <div class="card-icon">🚗</div>
        <div><div class="card-name">VOITURE</div><div class="card-detail">Extérieur · Intérieur · Vitres · Jantes</div></div>
        <div class="card-price">Dès 49€</div>
      </div>
      <div class="visual-card">
        <div class="card-icon">🏍️</div>
        <div><div class="card-name">MOTO</div><div class="card-detail">Carénages · Cadre · Roues</div></div>
        <div class="card-price">Dès 39€</div>
      </div>
      <div class="visual-card">
        <div class="card-icon">⛵</div>
        <div><div class="card-name">BATEAU</div><div class="card-detail">Coque · Pont · Cockpit · Au port</div></div>
        <div class="card-badge">Sur devis</div>
      </div>
      <div class="visual-card" style="border-color:rgba(245,200,66,0.25);background:rgba(245,200,66,0.06);">
        <div class="card-icon">💛</div>
        <div><div class="card-name" style="color:var(--gold);">CRÉDIT D'IMPÔT 50%</div><div class="card-detail">Tu récupères la moitié sur ta déclaration</div></div>
      </div>
    </div>
  </div>
</section>

</body>
</html><img width="1206" height="2622" alt="logo" src="https://github.com/user-attachments/assets/b8b5bf83-44c8-44d9-8b67-e153f2f4a499" />
<img width="1179" height="2556" alt="IMG_7418" src="https://github.com/user-attachments/assets/b36d0053-3ae3-4ee9-abea-44c041256224" />
