<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>WATERLESS — Détailing sans eau à domicile</title>
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }
:root { --black: #090909; --gold: #F5C842; --blue: #1A3A8F; --white: #F5F4F0; }

body {
  background: var(--black);
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  color: var(--white);
}

.bebas {
  font-family: 'Arial Black', 'Arial Bold', Impact, sans-serif;
  letter-spacing: 2px;
}

nav {
  padding: 0 4vw;
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  height: 80px;
  position: absolute;
  top: 0; left: 0; right: 0;
  z-index: 10;
  background: transparent;
  border-bottom: 1px solid rgba(245,200,66,0.25);
}
.nav-left { display: flex; gap: 2rem; align-items: center; justify-content: flex-end; }
.nav-center { display: flex; flex-direction: column; align-items: center; gap: 3px; padding: 0 2rem; }
.nav-right { display: flex; gap: 2rem; align-items: center; justify-content: flex-start; }
.nav-left a, .nav-right a {
  color: var(--white); text-decoration: none;
  font-size: 13px; letter-spacing: 2px; text-transform: uppercase; opacity: 0.85;
}
.nav-logo { width: 48px; height: 48px; object-fit: contain; }
.nav-logo-text {
  font-family: 'Arial Black', Impact, sans-serif;
  font-size: 16px; color: var(--gold); letter-spacing: 4px;
}

.hero {
  position: relative;
  min-height: 100vh;
  display: flex; align-items: center;
  overflow: hidden;
}
.hero-bg {
  position: absolute; inset: 0;
  background-image: url('IMG_7418.PNG');
  background-size: cover;
  background-position: center 25%;
  filter: brightness(0.55) saturate(0.7);
}
.hero-overlay {
  position: absolute; inset: 0;
  background: linear-gradient(90deg,
    rgba(9,9,9,0.95) 0%,
    rgba(9,9,9,0.7) 45%,
    rgba(9,9,9,0.15) 100%);
}
.hero-overlay-bottom {
  position: absolute; bottom: 0; left: 0; right: 0; height: 200px;
  background: linear-gradient(to top, rgba(9,9,9,1) 0%, transparent 100%);
}

.hero-inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  width: 100%;
  padding: calc(80px + 4rem) 4vw 4rem;
  position: relative; z-index: 2;
}

.hero-badge {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(245,200,66,0.1);
  border: 1px solid rgba(245,200,66,0.35);
  padding: 7px 16px; margin-bottom: 2rem;
  font-size: 10px; letter-spacing: 3px; text-transform: uppercase; color: var(--gold);
}
.dot {
  width: 6px; height: 6px; background: var(--gold); border-radius: 50%;
  animation: pulse 2s infinite;
}
@keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.2} }

.hero-title {
  font-family: 'Arial Black', Impact, sans-serif;
  font-size: clamp(52px, 7vw, 100px);
  line-height: 0.9;
  color: var(--white);
  margin-bottom: 1.5rem;
  text-transform: uppercase;
  letter-spacing: 2px;
}
.hero-title .gold { color: var(--gold); }
.hero-title .blue-out {
  -webkit-text-stroke: 2px #1A3A8F;
  color: transparent;
}

.hero-sub {
  font-size: 15px; color: rgba(245,244,240,0.6);
  line-height: 1.7; margin-bottom: 2.5rem; max-width: 480px;
}

.hero-actions { display: flex; gap: 12px; margin-bottom: 3rem; flex-wrap: wrap; }
.btn-primary {
  background: var(--gold); color: var(--black);
  padding: 14px 28px;
  font-family: 'Arial Black', Impact, sans-serif;
  font-size: 14px; letter-spacing: 2px; text-transform: uppercase;
  border: none; cursor: pointer;
}
.btn-ghost {
  background: rgba(26,58,143,0.2); color: rgba(245,244,240,0.9);
  padding: 14px 24px;
  font-family: 'Arial Black', Impact, sans-serif;
  font-size: 14px; letter-spacing: 2px; text-transform: uppercase;
  border: 1px solid rgba(26,58,143,0.5); cursor: pointer;
}

.hero-stats {
  display: flex; gap: 2rem; flex-wrap: wrap;
  padding-top: 2rem;
  border-top: 1px solid rgba(26,58,143,0.35);
}
.stat-num {
  font-family: 'Arial Black', Impact, sans-serif;
  font-size: 32px; color: var(--gold); line-height: 1;
}
.stat-label {
  font-size: 10px; color: rgba(245,244,240,0.4);
  letter-spacing: 2px; text-transform: uppercase; margin-top: 4px;
}

.hero-visual { display: flex; flex-direction: column; gap: 10px; }
.zone-tag {
  display: flex; align-items: center; gap: 8px;
  font-size: 10px; color: rgba(245,244,240,0.3);
  letter-spacing: 2px; text-transform: uppercase; margin-bottom: 4px;
}
.zone-line { flex: 1; height: 1px; background: rgba(245,200,66,0.12); }

.visual-card {
  background: rgba(9,9,9,0.7);
  border: 1px solid rgba(245,200,66,0.14);
  padding: 1rem 1.25rem;
  display: flex; align-items: center; gap: 1rem;
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
}
.visual-card.featured { border-color: rgba(245,200,66,0.45); }
.card-icon { font-size: 20px; width: 36px; text-align: center; flex-shrink: 0; }
.card-name {
  font-family: 'Arial Black', Impact, sans-serif;
  font-size: 15px; color: var(--white); letter-spacing: 1px; text-transform: uppercase;
}
.card-detail { font-size: 11px; color: rgba(245,244,240,0.4); margin-top: 3px; }
.card-price {
  margin-left: auto;
  font-family: 'Arial Black', Impact, sans-serif;
  font-size: 14px; color: var(--gold); flex-shrink: 0;
}
.card-badge {
  font-size: 9px; letter-spacing: 1.5px; text-transform: uppercase;
  background: rgba(245,200,66,0.1); color: rgba(245,200,66,0.8);
  padding: 3px 8px; margin-left: auto;
  border: 1px solid rgba(245,200,66,0.2);
}

@media (max-width: 768px) {
  nav { padding: 0 1.5rem; }
  .nav-left a, .nav-right a { font-size: 11px; gap: 1rem; }
  .nav-left { gap: 1rem; }
  .nav-right { gap: 1rem; }
  .hero-inner { grid-template-columns: 1fr; gap: 2rem; padding: calc(80px + 2rem) 1.5rem 2rem; }
  .hero-visual { display: none; }
  .hero-title { font-size: clamp(48px, 12vw, 80px); }
}
</style>
</head>
<body>

<nav>
  <div class="nav-left">
    <a href="#">Services</a>
    <a href="#">Comment ça marche</a>
  </div>
  <div class="nav-center">
    <img src="logo.PNG" class="nav-logo" alt="Water Less" />
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
      <h1 class="hero-title">
        DETAILING<br>
        <span class="gold">SANS EAU.</span><br>
        <span class="blue-out">CHEZ TOI.</span>
      </h1>
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
        <div><div class="card-name">Voiture</div><div class="card-detail">Extérieur · Intérieur · Vitres · Jantes</div></div>
        <div class="card-price">Dès 49€</div>
      </div>
      <div class="visual-card">
        <div class="card-icon">🏍️</div>
        <div><div class="card-name">Moto</div><div class="card-detail">Carénages · Cadre · Roues</div></div>
        <div class="card-price">Dès 39€</div>
      </div>
      <div class="visual-card">
        <div class="card-icon">⛵</div>
        <div><div class="card-name">Bateau</div><div class="card-detail">Coque · Pont · Cockpit · Au port</div></div>
        <div class="card-badge">Sur devis</div>
      </div>
      <div class="visual-card" style="border-color:rgba(245,200,66,0.25);background:rgba(245,200,66,0.05);">
        <div class="card-icon">💛</div>
        <div>
          <div class="card-name" style="color:var(--gold);">Crédit d'impôt 50%</div>
          <div class="card-detail">Tu récupères la moitié sur ta déclaration</div>
        </div>
      </div>
    </div>
  </div>
</section>

</body>
</html>
