# aurapods
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aurapods</title>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #F7F6F3;
    --surface: #FFFFFF;
    --surface-2: #F0EEE9;
    --border: #E8E5DF;
    --accent: #7C6AF5;
    --accent-soft: #EEECff;
    --accent-mid: #C4BEF9;
    --text: #1C1A17;
    --text-2: #6B6860;
    --text-3: #A8A49E;
    --green: #2D9E6B;
    --green-soft: #E4F5EE;
    --radius: 16px;
    --radius-sm: 10px;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Plus Jakarta Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* HEADER */
  header {
    padding: 18px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: var(--bg);
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .logo {
    font-size: 20px;
    font-weight: 800;
    color: var(--text);
    letter-spacing: -0.04em;
  }
  .logo-dot { color: var(--accent); }

  .live-pill {
    display: flex;
    align-items: center;
    gap: 6px;
    background: var(--green-soft);
    color: var(--green);
    font-size: 11px;
    font-weight: 600;
    padding: 6px 12px;
    border-radius: 100px;
  }
  .live-dot {
    width: 6px; height: 6px;
    background: var(--green);
    border-radius: 50%;
    animation: pulse 1.6s ease-in-out infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  /* HERO */
  .hero {
    padding: 28px 20px 24px;
  }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--accent-soft);
    color: var(--accent);
    font-size: 11px;
    font-weight: 600;
    padding: 5px 12px;
    border-radius: 100px;
    margin-bottom: 16px;
    letter-spacing: 0.02em;
  }

  .hero h1 {
    font-size: clamp(32px, 9vw, 48px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.04em;
    color: var(--text);
    margin-bottom: 12px;
  }
  .hero h1 .underline {
    position: relative;
    display: inline-block;
  }
  .hero h1 .underline::after {
    content: '';
    position: absolute;
    bottom: 2px;
    left: 0;
    right: 0;
    height: 3px;
    background: var(--accent-mid);
    border-radius: 100px;
  }

  .hero-sub {
    font-size: 14px;
    color: var(--text-2);
    line-height: 1.6;
    margin-bottom: 22px;
  }

  /* STATS ROW */
  .stats-row {
    display: flex;
    gap: 8px;
    margin-bottom: 8px;
  }
  .stat-chip {
    flex: 1;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    padding: 12px 10px;
    text-align: center;
    box-shadow: 0 1px 4px rgba(0,0,0,0.04);
  }
  .stat-val {
    font-size: 18px;
    font-weight: 800;
    color: var(--text);
    letter-spacing: -0.03em;
  }
  .stat-label {
    font-size: 10px;
    color: var(--text-3);
    font-weight: 500;
    margin-top: 2px;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  /* SECTION */
  .section-head {
    padding: 24px 20px 12px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .section-title {
    font-size: 17px;
    font-weight: 700;
    letter-spacing: -0.02em;
    color: var(--text);
  }
  .section-sub {
    font-size: 12px;
    color: var(--text-3);
    font-weight: 500;
  }

  /* FILTERS */
  .filters {
    padding: 0 20px 16px;
    display: flex;
    gap: 6px;
    overflow-x: auto;
    scrollbar-width: none;
  }
  .filters::-webkit-scrollbar { display: none; }
  .filter-btn {
    flex-shrink: 0;
    padding: 7px 14px;
    border-radius: 100px;
    border: 1px solid var(--border);
    background: var(--surface);
    color: var(--text-2);
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s;
  }
  .filter-btn.active {
    background: var(--accent);
    border-color: var(--accent);
    color: #fff;
    box-shadow: 0 4px 12px rgba(124,106,245,0.3);
  }
  .filter-btn:hover:not(.active) {
    border-color: var(--accent-mid);
    color: var(--accent);
  }

  /* GRID */
  .grid {
    padding: 0 16px 16px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
  }

  .card {
    background: var(--surface);
    border-radius: var(--radius);
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    border: 1px solid var(--border);
    box-shadow: 0 2px 8px rgba(0,0,0,0.04);
    animation: fadeUp 0.35s ease both;
  }
  .card:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 32px rgba(0,0,0,0.09);
  }
  .card:active { transform: scale(0.98); }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(14px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .card:nth-child(1) { animation-delay: 0.04s; }
  .card:nth-child(2) { animation-delay: 0.08s; }
  .card:nth-child(3) { animation-delay: 0.12s; }
  .card:nth-child(4) { animation-delay: 0.16s; }
  .card:nth-child(5) { animation-delay: 0.20s; }
  .card:nth-child(6) { animation-delay: 0.24s; }

  .card-img-wrap {
    position: relative;
    aspect-ratio: 1/1;
    background: var(--surface-2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 52px;
  }

  .badge {
    position: absolute;
    top: 8px;
    left: 8px;
    font-size: 9px;
    font-weight: 700;
    padding: 3px 8px;
    border-radius: 100px;
    letter-spacing: 0.04em;
    text-transform: uppercase;
  }
  .badge-hot { background: #FFF0E6; color: #E06C1F; }
  .badge-new { background: var(--green-soft); color: var(--green); }
  .badge-deal { background: var(--accent-soft); color: var(--accent); }

  .card-body { padding: 11px 12px 13px; }

  .card-cat {
    font-size: 9px;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--text-3);
    margin-bottom: 3px;
  }

  .card-name {
    font-size: 13px;
    font-weight: 700;
    line-height: 1.3;
    color: var(--text);
    margin-bottom: 10px;
    letter-spacing: -0.01em;
  }

  .card-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .card-price {
    font-size: 18px;
    font-weight: 800;
    color: var(--text);
    letter-spacing: -0.03em;
  }

  .card-btn {
    width: 30px; height: 30px;
    background: var(--accent-soft);
    border: none;
    border-radius: 8px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background 0.15s, transform 0.15s;
    color: var(--accent);
    font-size: 14px;
  }
  .card-btn:hover { background: var(--accent); color: #fff; transform: scale(1.05); }

  /* TRUST */
  .trust-row {
    margin: 4px 16px 4px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
  }
  .trust-chip {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    padding: 12px 8px;
    text-align: center;
    box-shadow: 0 1px 4px rgba(0,0,0,0.03);
  }
  .trust-icon { font-size: 18px; margin-bottom: 4px; }
  .trust-text { font-size: 9px; font-weight: 600; color: var(--text-2); text-transform: uppercase; letter-spacing: 0.06em; }

  /* MODAL */
  .modal-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(28, 26, 23, 0.45);
    z-index: 1000;
    align-items: flex-end;
    justify-content: center;
    backdrop-filter: blur(4px);
  }
  .modal-overlay.open {
    display: flex;
    animation: fadeIn 0.15s ease;
  }
  @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

  .modal {
    background: var(--surface);
    border-radius: 24px 24px 0 0;
    width: 100%;
    max-width: 520px;
    padding: 8px 0 0;
    animation: slideUp 0.3s cubic-bezier(0.34, 1.15, 0.64, 1);
    max-height: 90vh;
    overflow-y: auto;
  }
  @keyframes slideUp {
    from { transform: translateY(50px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
  }

  .modal-handle {
    width: 32px; height: 4px;
    background: var(--border);
    border-radius: 100px;
    margin: 0 auto 20px;
  }

  .modal-inner { padding: 0 20px 40px; }

  .modal-img {
    width: 100%;
    aspect-ratio: 16/9;
    background: var(--surface-2);
    border-radius: var(--radius);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 80px;
    margin-bottom: 20px;
    border: 1px solid var(--border);
  }

  .modal-cat {
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--text-3);
    margin-bottom: 5px;
  }

  .modal-name {
    font-size: 24px;
    font-weight: 800;
    letter-spacing: -0.03em;
    color: var(--text);
    margin-bottom: 6px;
    line-height: 1.15;
  }

  .modal-price {
    font-size: 32px;
    font-weight: 800;
    color: var(--accent);
    letter-spacing: -0.04em;
    margin-bottom: 14px;
  }

  .modal-desc {
    font-size: 13px;
    color: var(--text-2);
    line-height: 1.65;
    margin-bottom: 22px;
    padding-bottom: 20px;
    border-bottom: 1px solid var(--border);
  }

  .modal-actions { display: flex; flex-direction: column; gap: 10px; }

  .btn-main {
    background: var(--accent);
    color: #fff;
    border: none;
    border-radius: var(--radius-sm);
    padding: 16px;
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 700;
    font-size: 14px;
    cursor: pointer;
    transition: opacity 0.15s, transform 0.15s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    text-decoration: none;
    box-shadow: 0 4px 16px rgba(124,106,245,0.3);
  }
  .btn-main:hover { opacity: 0.92; transform: translateY(-1px); }

  .btn-ghost {
    background: transparent;
    color: var(--text-2);
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    padding: 15px;
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    transition: border-color 0.15s, color 0.15s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    text-decoration: none;
  }
  .btn-ghost:hover { border-color: var(--accent-mid); color: var(--accent); }

  /* FOOTER */
  footer {
    padding: 24px 20px 48px;
    text-align: center;
    font-size: 11px;
    color: var(--text-3);
    font-weight: 500;
    letter-spacing: 0.04em;
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="logo">Aurapods<span class="logo-dot">.</span></div>
  <div class="live-pill">
    <span class="live-dot"></span>
    En ligne
  </div>
</header>

<!-- HERO -->
<section class="hero">
  <div class="hero-tag">✦ Sélection du moment</div>
  <h1>Pièces <span class="underline">uniques</span>,<br>prix justes.</h1>
  <p class="hero-sub">Streetwear & tech vérifiés. Chaque article sélectionné à la main, livré rapidement.</p>
  <div class="stats-row">
    <div class="stat-chip">
      <div class="stat-val" id="stat-count">6</div>
      <div class="stat-label">Dispo</div>
    </div>
    <div class="stat-chip">
      <div class="stat-val">24h</div>
      <div class="stat-label">Livraison</div>
    </div>
    <div class="stat-chip">
      <div class="stat-val">100%</div>
      <div class="stat-label">Vérifié</div>
    </div>
  </div>
</section>

<!-- SECTION HEAD + FILTERS -->
<div class="section-head">
  <div class="section-title">Les articles</div>
  <div class="section-sub" id="prod-count">6 articles</div>
</div>
<div class="filters">
  <button class="filter-btn active" onclick="filterProducts('all', this)">Tout</button>
  <button class="filter-btn" onclick="filterProducts('streetwear', this)">Streetwear</button>
  <button class="filter-btn" onclick="filterProducts('tech', this)">Tech & Audio</button>
</div>

<!-- GRID -->
<div class="grid" id="grid"></div>

<!-- TRUST -->
<div class="trust-row">
  <div class="trust-chip">
    <div class="trust-icon">🔍</div>
    <div class="trust-text">Vérifié</div>
  </div>
  <div class="trust-chip">
    <div class="trust-icon">📦</div>
    <div class="trust-text">Livraison 24h</div>
  </div>
  <div class="trust-chip">
    <div class="trust-icon">🔒</div>
    <div class="trust-text">Sécurisé</div>
  </div>
</div>

<!-- MODAL -->
<div class="modal-overlay" id="modal" onclick="closeModal(event)">
  <div class="modal">
    <div class="modal-handle"></div>
    <div class="modal-inner">
      <div class="modal-img" id="modal-emoji"></div>
      <div class="modal-cat" id="modal-cat"></div>
      <div class="modal-name" id="modal-name"></div>
      <div class="modal-price" id="modal-price"></div>
      <div class="modal-desc" id="modal-desc"></div>
      <div class="modal-actions" id="modal-actions"></div>
    </div>
  </div>
</div>

<footer>© 2025 Aurapods · Tous droits réservés</footer>

<script>
const WHATSAPP = "33660146630"; // ← Ton numéro ici

const products = [
  { id:1, name:"CDG PLAY Heart Tee", category:"streetwear", emoji:"🤍", badge:"Hot", badgeClass:"badge-hot", price:85, desc:"T-shirt Comme des Garçons PLAY avec patch cœur brodé. Taille M. Excellent état, porté 2 fois. Authentique avec facture.", payment:"whatsapp" },
  { id:2, name:"AirPods 4", category:"tech", emoji:"https://ibb.co/fzfT32CM", badge:"Top Deal", badgeClass:"badge-deal", price:149, desc:"AirPods Pro 2ème génération  Inclus câble USB-C et embouts neufs.", payment:"stripe" },
  { id:3, name:"CP Company Goggle Jacket", category:"streetwear", emoji:"🧥", badge:null, price:310, desc:"Veste CP Company avec lunettes intégrées. Taille L. Coloris olive. Légères traces d'usure sur les poignets. Authentique.", payment:"whatsapp" },
  { id:4, name:"iPhone 13 Pro 128Go", category:"tech", emoji:"📱", badge:"Débloqué", badgeClass:"badge-new", price:420, desc:"iPhone 13 Pro 128Go coloris graphite. Batterie 89%. Écran parfait, boîtier impeccable. Débloqué tous opérateurs.", payment:"stripe" },
  { id:5, name:"Nike Tech Fleece Set", category:"streetwear", emoji:"🖤", badge:null, price:95, desc:"Ensemble Nike Tech Fleece veste + jogging. Coloris noir. Taille M. Porté quelques fois, très bon état général.", payment:"whatsapp" },
  { id:6, name:"Galaxy Buds2 Pro", category:"tech", emoji:"🎵", badge:"Neuf", badgeClass:"badge-new", price:89, desc:"Samsung Galaxy Buds2 Pro, jamais utilisés. Boîte ouverte uniquement pour vérification. Garantie constructeur active.", payment:"stripe" }
];

function renderProducts(filter = 'all') {
  const grid = document.getElementById('grid');
  grid.innerHTML = '';
  const filtered = filter === 'all' ? products : products.filter(p => p.category === filter);
  document.getElementById('prod-count').textContent = filtered.length + ' article' + (filtered.length > 1 ? 's' : '');
  document.getElementById('stat-count').textContent = products.length;

  filtered.forEach((p, i) => {
    const card = document.createElement('div');
    card.className = 'card';
    card.style.animationDelay = (i * 0.06) + 's';
    card.onclick = () => openModal(p);
    card.innerHTML = `
      <div class="card-img-wrap">
        <span>${p.emoji}</span>
        ${p.badge ? `<span class="badge ${p.badgeClass || ''}">${p.badge}</span>` : ''}
      </div>
      <div class="card-body">
        <div class="card-cat">${p.category === 'tech' ? 'Tech & Audio' : 'Streetwear'}</div>
        <div class="card-name">${p.name}</div>
        <div class="card-footer">
          <span class="card-price">${p.price}€</span>
          <button class="card-btn">→</button>
        </div>
      </div>
    `;
    grid.appendChild(card);
  });
}

function filterProducts(cat, btn) {
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderProducts(cat);
}

function openModal(p) {
  document.getElementById('modal-emoji').textContent = p.emoji;
  document.getElementById('modal-cat').textContent = p.category === 'tech' ? 'Tech & Audio' : 'Streetwear';
  document.getElementById('modal-name').textContent = p.name;
  document.getElementById('modal-price').textContent = p.price + '€';
  document.getElementById('modal-desc').textContent = p.desc;

  const actions = document.getElementById('modal-actions');
  const waMsg = encodeURIComponent(`Salut ! Je suis intéressé par : ${p.name} à ${p.price}€`);

  if (p.payment === 'stripe') {
    actions.innerHTML = `
      <button class="btn-main" onclick="alert('Stripe à connecter avec ta clé API 🔑')">
        💳 Payer par carte — ${p.price}€
      </button>
      <a class="btn-ghost" href="https://wa.me/${WHATSAPP}?text=${waMsg}" target="_blank">
        💬 Contacter sur WhatsApp
      </a>
    `;
  } else {
    actions.innerHTML = `
      <a class="btn-main" href="https://wa.me/${WHATSAPP}?text=${waMsg}" target="_blank">
        💬 Commander via WhatsApp
      </a>
      <p style="text-align:center; font-size:11px; color:var(--text-3); margin-top:4px;">Paiement par virement ou Lydia après confirmation</p>
    `;
  }

  document.getElementById('modal').classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeModal(e) {
  if (e.target === document.getElementById('modal')) {
    document.getElementById('modal').classList.remove('open');
    document.body.style.overflow = '';
  }
}

renderProducts();
</script>
</body>
</html>
