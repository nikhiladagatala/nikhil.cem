<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BiogasCalc — Vegetable Waste Energy Estimator</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Mono:wght@300;400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --soil:    #1a160e;
    --bark:    #2d2416;
    --moss:    #3b4a2a;
    --leaf:    #5a7a3a;
    --lime:    #8db84a;
    --sprout:  #b8d96e;
    --mist:    #e8f0d4;
    --cream:   #f5f0e8;
    --amber:   #d4a448;
    --flame:   #e07830;
    --glow:    #f5c842;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--soil);
    color: var(--cream);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── BACKGROUND TEXTURE ── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 20% 10%, rgba(91,122,58,.18) 0%, transparent 70%),
      radial-gradient(ellipse 60% 80% at 80% 90%, rgba(26,45,20,.4) 0%, transparent 60%),
      url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence baseFrequency='.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
  }

  .wrap { position: relative; z-index: 1; max-width: 900px; margin: 0 auto; padding: 0 24px 80px; }

  /* ── HEADER ── */
  header {
    padding: 60px 0 40px;
    display: flex; flex-direction: column; gap: 12px;
    border-bottom: 1px solid rgba(184,217,110,.15);
    margin-bottom: 48px;
    animation: fadeDown .8s ease both;
  }
  .eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: .7rem; letter-spacing: .2em; text-transform: uppercase;
    color: var(--lime); opacity: .8;
  }
  h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 6vw, 3.6rem);
    font-weight: 700; line-height: 1.1;
    color: var(--mist);
  }
  h1 em { color: var(--sprout); font-style: italic; }
  .sub {
    font-size: .95rem; color: rgba(232,240,212,.55);
    max-width: 520px; line-height: 1.6;
  }

  /* ── GRID ── */
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
  @media(max-width:640px) { .grid { grid-template-columns: 1fr; } }

  /* ── CARD ── */
  .card {
    background: rgba(45,36,22,.6);
    border: 1px solid rgba(184,217,110,.12);
    border-radius: 16px;
    padding: 28px 28px 24px;
    backdrop-filter: blur(12px);
    transition: border-color .3s;
  }
  .card:hover { border-color: rgba(184,217,110,.28); }
  .card-label {
    font-family: 'DM Mono', monospace;
    font-size: .65rem; letter-spacing: .18em; text-transform: uppercase;
    color: var(--lime); margin-bottom: 20px; opacity: .75;
  }

  /* ── WASTE ROWS ── */
  .waste-row {
    display: grid; grid-template-columns: 1fr auto;
    align-items: center; gap: 12px;
    margin-bottom: 14px;
    animation: fadeUp .5s ease both;
  }
  .waste-info { display: flex; flex-direction: column; gap: 3px; }
  .waste-name {
    font-size: .88rem; font-weight: 500; color: var(--mist);
    display: flex; align-items: center; gap: 7px;
  }
  .waste-name span { font-size: 1.1rem; }
  .waste-yield {
    font-family: 'DM Mono', monospace;
    font-size: .65rem; color: rgba(184,217,110,.5);
  }
  .qty-wrap { display: flex; align-items: center; gap: 6px; }
  .qty-input {
    width: 72px;
    background: rgba(26,22,14,.7);
    border: 1px solid rgba(184,217,110,.2);
    border-radius: 8px;
    color: var(--sprout);
    font-family: 'DM Mono', monospace;
    font-size: .9rem;
    padding: 6px 10px;
    text-align: right;
    outline: none;
    transition: border-color .25s, box-shadow .25s;
  }
  .qty-input:focus {
    border-color: var(--lime);
    box-shadow: 0 0 0 3px rgba(141,184,74,.12);
  }
  .unit { font-size: .72rem; color: rgba(232,240,212,.4); width: 22px; }

  /* ── PARAMS ── */
  .param-row {
    display: flex; flex-direction: column; gap: 6px;
    margin-bottom: 16px;
  }
  .param-label {
    font-size: .8rem; color: rgba(232,240,212,.6);
    display: flex; justify-content: space-between;
  }
  .param-label strong {
    font-family: 'DM Mono', monospace;
    font-size: .78rem; color: var(--sprout); font-weight: 400;
  }
  input[type=range] {
    -webkit-appearance: none; appearance: none;
    width: 100%; height: 4px;
    background: rgba(184,217,110,.2);
    border-radius: 999px; outline: none; cursor: pointer;
  }
  input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 16px; height: 16px;
    border-radius: 50%;
    background: var(--lime);
    box-shadow: 0 0 8px rgba(141,184,74,.5);
    transition: transform .2s;
  }
  input[type=range]::-webkit-slider-thumb:active { transform: scale(1.25); }

  /* ── FULL-WIDTH RESULT CARD ── */
  .result-card {
    grid-column: 1 / -1;
    background: linear-gradient(135deg, rgba(59,74,42,.55) 0%, rgba(26,22,14,.7) 100%);
    border: 1px solid rgba(141,184,74,.25);
    border-radius: 16px;
    padding: 36px 32px 32px;
    animation: fadeUp .6s .1s ease both;
  }

  .result-grid {
    display: grid;
    grid-template-columns: repeat(4,1fr);
    gap: 20px;
    margin-top: 24px;
  }
  @media(max-width:580px) { .result-grid { grid-template-columns: 1fr 1fr; } }

  .metric {
    display: flex; flex-direction: column; gap: 6px;
    padding: 18px 16px;
    background: rgba(26,22,14,.5);
    border: 1px solid rgba(184,217,110,.1);
    border-radius: 12px;
    transition: border-color .3s, transform .3s;
  }
  .metric:hover { border-color: rgba(184,217,110,.3); transform: translateY(-2px); }
  .metric-icon { font-size: 1.4rem; line-height: 1; }
  .metric-value {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.4rem, 3vw, 2rem);
    color: var(--sprout); font-weight: 700; line-height: 1;
  }
  .metric-unit {
    font-family: 'DM Mono', monospace;
    font-size: .65rem; color: rgba(232,240,212,.45); text-transform: uppercase; letter-spacing: .12em;
  }
  .metric-label { font-size: .75rem; color: rgba(232,240,212,.5); margin-top: 2px; }

  /* ── BAR ── */
  .bar-section { margin-top: 28px; }
  .bar-title {
    font-size: .75rem; color: rgba(232,240,212,.4);
    font-family: 'DM Mono', monospace; letter-spacing: .12em; text-transform: uppercase;
    margin-bottom: 14px;
  }
  .bar-row { display: flex; align-items: center; gap: 10px; margin-bottom: 10px; }
  .bar-name { font-size: .78rem; color: var(--mist); width: 120px; flex-shrink: 0; }
  .bar-track {
    flex: 1; height: 8px;
    background: rgba(255,255,255,.06);
    border-radius: 999px; overflow: hidden;
  }
  .bar-fill {
    height: 100%; border-radius: 999px;
    background: linear-gradient(90deg, var(--moss), var(--lime));
    transition: width .8s cubic-bezier(.16,1,.3,1);
  }
  .bar-pct {
    font-family: 'DM Mono', monospace;
    font-size: .68rem; color: var(--lime); width: 36px; text-align: right;
  }

  /* ── BUTTON ── */
  .btn-calc {
    display: inline-flex; align-items: center; gap: 10px;
    margin-top: 8px;
    background: linear-gradient(135deg, var(--leaf), var(--lime));
    color: var(--soil);
    font-family: 'DM Sans', sans-serif;
    font-weight: 500; font-size: .88rem;
    padding: 12px 28px; border-radius: 999px;
    border: none; cursor: pointer;
    box-shadow: 0 4px 20px rgba(141,184,74,.25);
    transition: transform .2s, box-shadow .2s;
  }
  .btn-calc:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 28px rgba(141,184,74,.38);
  }
  .btn-calc:active { transform: translateY(0); }

  /* ── NOTE ── */
  .note {
    margin-top: 28px;
    padding: 16px 20px;
    background: rgba(212,164,72,.07);
    border-left: 3px solid var(--amber);
    border-radius: 0 10px 10px 0;
    font-size: .78rem; color: rgba(232,240,212,.5); line-height: 1.6;
  }
  .note strong { color: var(--amber); font-weight: 500; }

  /* ── ANIMATIONS ── */
  @keyframes fadeDown { from { opacity:0; transform:translateY(-18px); } to { opacity:1; transform:translateY(0); } }
  @keyframes fadeUp   { from { opacity:0; transform:translateY(18px); } to { opacity:1; transform:translateY(0); } }

  /* ── FLAME PULSE ── */
  .flame-pulse { display: inline-block; animation: flamePulse 2s ease-in-out infinite; }
  @keyframes flamePulse {
    0%,100% { transform: scale(1) rotate(-3deg); }
    50%      { transform: scale(1.15) rotate(3deg); }
  }
</style>
</head>
<body>
<div class="wrap">

  <header>
    <div class="eyebrow">Renewable Energy Estimator</div>
    <h1>Biogas from <em>Vegetable Waste</em></h1>
    <p class="sub">Estimate methane yield, cooking hours, and CO₂ offset from your kitchen or farm vegetable scraps.</p>
  </header>

  <div class="grid">

    <!-- WASTE INPUT -->
    <div class="card" style="animation: fadeUp .5s .05s ease both">
      <div class="card-label">Waste Input (kg/day)</div>

      <div id="waste-list"></div>

      <button class="btn-calc" onclick="calculate()">
        <span class="flame-pulse">🔥</span> Calculate Biogas
      </button>
    </div>

    <!-- PARAMETERS -->
    <div class="card" style="animation: fadeUp .5s .1s ease both">
      <div class="card-label">Process Parameters</div>

      <div class="param-row">
        <div class="param-label">Digester Temperature <strong id="tempVal">35 °C</strong></div>
        <input type="range" id="temp" min="20" max="55" value="35" oninput="updateTemp(this.value)">
      </div>

      <div class="param-row">
        <div class="param-label">Retention Time <strong id="hrtVal">30 days</strong></div>
        <input type="range" id="hrt" min="10" max="60" value="30" oninput="updateHRT(this.value)">
      </div>

      <div class="param-row">
        <div class="param-label">Digester Efficiency <strong id="effVal">70%</strong></div>
        <input type="range" id="eff" min="40" max="95" value="70" oninput="updateEff(this.value)">
      </div>

      <div class="param-row">
        <div class="param-label">CH₄ Content in Biogas <strong id="ch4Val">60%</strong></div>
        <input type="range" id="ch4" min="50" max="75" value="60" oninput="updateCH4(this.value)">
      </div>

      <div class="param-row">
        <div class="param-label">Moisture Content of Waste <strong id="moistVal">80%</strong></div>
        <input type="range" id="moist" min="50" max="95" value="80" oninput="updateMoist(this.value)">
      </div>
    </div>

    <!-- RESULTS -->
    <div class="result-card">
      <div class="card-label">Estimated Daily Output</div>

      <div class="result-grid">
        <div class="metric">
          <div class="metric-icon">🌿</div>
          <div class="metric-value" id="r-rawWaste">0</div>
          <div class="metric-unit">kg / day</div>
          <div class="metric-label">Total Waste Input</div>
        </div>
        <div class="metric">
          <div class="metric-icon">⚗️</div>
          <div class="metric-value" id="r-biogas">0</div>
          <div class="metric-unit">m³ / day</div>
          <div class="metric-label">Biogas Produced</div>
        </div>
        <div class="metric">
          <div class="metric-icon">🔥</div>
          <div class="metric-value" id="r-methane">0</div>
          <div class="metric-unit">m³ CH₄/day</div>
          <div class="metric-label">Methane (CH₄)</div>
        </div>
        <div class="metric">
          <div class="metric-icon">⚡</div>
          <div class="metric-value" id="r-energy">0</div>
          <div class="metric-unit">kWh / day</div>
          <div class="metric-label">Energy Equivalent</div>
        </div>
        <div class="metric">
          <div class="metric-icon">🍳</div>
          <div class="metric-value" id="r-cooking">0</div>
          <div class="metric-unit">hrs cooking</div>
          <div class="metric-label">Stove Hours/day</div>
        </div>
        <div class="metric">
          <div class="metric-icon">🌍</div>
          <div class="metric-value" id="r-co2">0</div>
          <div class="metric-unit">kg CO₂/day</div>
          <div class="metric-label">CO₂ Offset</div>
        </div>
        <div class="metric">
          <div class="metric-icon">💡</div>
          <div class="metric-value" id="r-bulbs">0</div>
          <div class="metric-unit">bulbs (8W)</div>
          <div class="metric-label">LED Bulbs Powered</div>
        </div>
        <div class="metric">
          <div class="metric-icon">🌱</div>
          <div class="metric-value" id="r-slurry">0</div>
          <div class="metric-unit">kg / day</div>
          <div class="metric-label">Bio-slurry (fertilizer)</div>
        </div>
      </div>

      <!-- BAR BREAKDOWN -->
      <div class="bar-section">
        <div class="bar-title">Waste Contribution Breakdown</div>
        <div id="bar-rows"></div>
      </div>

      <div class="note">
        <strong>Methodology:</strong> Biogas yield = (Dry Mass × Volatile Solids fraction × Biogas Yield Factor × Digester Efficiency × Temperature Factor × HRT Factor).
        CH₄ energy = 9.97 kWh/m³. CO₂ offset assumes displaced LPG (2.98 kg CO₂/kg LPG, 13.8 kWh/kg).
        Values are indicative estimates for planning; actual yields depend on feedstock quality, digester design, and microbial activity.
      </div>
    </div>

  </div>
</div>

<script>
/* ── WASTE DATA ──
   bioYield: m³ biogas per kg Volatile Solids (VS)
   vsFraction: VS as fraction of Dry Matter
   dmFraction: Dry Matter as fraction of wet weight (typical)
*/
const WASTES = [
  { emoji:'🥕', name:'Carrot peels',     kg:0, bioYield:.42, vsFrac:.88, dm:.1  },
  { emoji:'🍅', name:'Tomato scraps',    kg:0, bioYield:.38, vsFrac:.82, dm:.06 },
  { emoji:'🥬', name:'Leafy greens',     kg:0, bioYield:.30, vsFrac:.80, dm:.08 },
  { emoji:'🥔', name:'Potato peels',     kg:0, bioYield:.45, vsFrac:.85, dm:.20 },
  { emoji:'🧅', name:'Onion waste',      kg:0, bioYield:.35, vsFrac:.85, dm:.09 },
  { emoji:'🌽', name:'Corn cobs/husks',  kg:0, bioYield:.50, vsFrac:.90, dm:.15 },
  { emoji:'🍌', name:'Banana peels',     kg:0, bioYield:.32, vsFrac:.78, dm:.20 },
  { emoji:'🍊', name:'Citrus peels',     kg:0, bioYield:.22, vsFrac:.85, dm:.25 },
  { emoji:'🫑', name:'Capsicum/pepper',  kg:0, bioYield:.36, vsFrac:.83, dm:.07 },
  { emoji:'🎃', name:'Pumpkin waste',    kg:0, bioYield:.44, vsFrac:.88, dm:.09 },
];

function tempFactor(t) {
  // mesophilic optimum ~35°C, thermophilic ~55°C
  if (t >= 50) return 1.25;
  if (t >= 35) return 1.0 + (t-35)*0.015;
  return 0.6 + (t-20)*0.027;
}
function hrtFactor(h) {
  // longer HRT = better VS destruction, diminishing returns
  return Math.min(1, 0.55 + (h-10)*0.015);
}

function buildWasteList() {
  const el = document.getElementById('waste-list');
  el.innerHTML = WASTES.map((w,i) => `
    <div class="waste-row" style="animation-delay:${i*0.04}s">
      <div class="waste-info">
        <div class="waste-name"><span>${w.emoji}</span>${w.name}</div>
        <div class="waste-yield">~${(w.bioYield).toFixed(2)} m³ biogas/kg VS</div>
      </div>
      <div class="qty-wrap">
        <input class="qty-input" type="number" min="0" step="0.5" value="0"
               id="w${i}" oninput="WASTES[${i}].kg=parseFloat(this.value)||0">
        <span class="unit">kg</span>
      </div>
    </div>`).join('');
}

function calculate() {
  const eff   = parseFloat(document.getElementById('eff').value)/100;
  const ch4Pct= parseFloat(document.getElementById('ch4').value)/100;
  const temp  = parseFloat(document.getElementById('temp').value);
  const hrt   = parseFloat(document.getElementById('hrt').value);
  const moist = parseFloat(document.getElementById('moist').value)/100;
  const tf = tempFactor(temp), hf = hrtFactor(hrt);

  let totalKg = 0, totalBiogas = 0;
  const contributions = [];

  WASTES.forEach(w => {
    if (!w.kg) { contributions.push(0); return; }
    // use slider moisture override for 'dm' approximation
    const dm = Math.max(0.02, w.dm * (1 - moist*0.4));
    const dryMass = w.kg * dm;
    const vs = dryMass * w.vsFrac;
    const gas = vs * w.bioYield * eff * tf * hf;
    contributions.push(gas);
    totalKg += w.kg;
    totalBiogas += gas;
  });

  const methane = totalBiogas * ch4Pct;
  const energy  = methane * 9.97;            // kWh
  const cooking = methane / 0.45;            // ~0.45 m³ CH4/hr for stove
  // CO₂ offset: displaced LPG — 1 kWh LPG ≈ 0.216 kg CO₂
  const co2     = energy * 0.216;
  const bulbs   = energy / (8/1000) / 24;    // 8W bulbs for 24h
  const slurry  = totalKg * 0.92;            // ~92% becomes effluent

  set('r-rawWaste', fmt(totalKg));
  set('r-biogas',   fmt(totalBiogas));
  set('r-methane',  fmt(methane));
  set('r-energy',   fmt(energy));
  set('r-cooking',  fmt(cooking,1));
  set('r-co2',      fmt(co2));
  set('r-bulbs',    fmt(bulbs,0));
  set('r-slurry',   fmt(slurry));

  // bars
  const max = Math.max(...contributions, 0.001);
  const barEl = document.getElementById('bar-rows');
  barEl.innerHTML = WASTES.map((w,i) => {
    const pct = contributions[i]/max*100;
    const abs = contributions[i];
    if (abs === 0) return '';
    return `<div class="bar-row">
      <div class="bar-name">${w.emoji} ${w.name}</div>
      <div class="bar-track"><div class="bar-fill" style="width:${pct}%"></div></div>
      <div class="bar-pct">${fmt(abs,2)}</div>
    </div>`;
  }).join('');
}

function set(id, v) { document.getElementById(id).textContent = v; }
function fmt(v, d=2) { return v.toLocaleString(undefined,{minimumFractionDigits:d,maximumFractionDigits:d}); }

function updateTemp(v) { document.getElementById('tempVal').textContent = v+' °C'; }
function updateHRT(v)  { document.getElementById('hrtVal').textContent  = v+' days'; }
function updateEff(v)  { document.getElementById('effVal').textContent  = v+'%'; }
function updateCH4(v)  { document.getElementById('ch4Val').textContent  = v+'%'; }
function updateMoist(v){ document.getElementById('moistVal').textContent= v+'%'; }

buildWasteList();

// pre-fill demo values
const demo = [2,1.5,1,2.5,0.5,0,1,0,0,1];
demo.forEach((v,i)=>{
  WASTES[i].kg = v;
  const el = document.getElementById('w'+i);
  if(el) el.value = v;
});
calculate();
</script>
</body>
</html>
