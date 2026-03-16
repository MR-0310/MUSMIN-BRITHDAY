<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Musmin Taj 💖</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Dancing+Script:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --rose: #ff2d6b;
    --pink: #ff6fa8;
    --blush: #ffd6e7;
    --gold: #ffd700;
    --deep: #1a0010;
    --magenta: #c2185b;
    --white: #fff8fc;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #0d0006;
    font-family: 'Playfair Display', serif;
    overflow-x: hidden;
    cursor: none;
    min-height: 100vh;
  }

  /* Custom cursor */
  .cursor {
    width: 18px; height: 18px;
    background: var(--rose);
    border-radius: 50%;
    position: fixed;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s ease;
    box-shadow: 0 0 18px var(--rose);
  }

  /* ---- CANVAS for particles ---- */
  #canvas {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
  }

  /* ---- HERO ---- */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    z-index: 1;
    text-align: center;
    padding: 40px 20px;
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 50% 50%, rgba(194,24,91,0.18) 0%, transparent 70%),
      radial-gradient(ellipse 40% 30% at 20% 80%, rgba(255,45,107,0.12) 0%, transparent 60%),
      radial-gradient(ellipse 40% 30% at 80% 20%, rgba(255,215,0,0.07) 0%, transparent 60%);
    pointer-events: none;
  }

  .crown {
    font-size: 3rem;
    animation: float 3s ease-in-out infinite;
    display: block;
    margin-bottom: 8px;
  }

  .hero-label {
    font-family: 'Dancing Script', cursive;
    color: var(--gold);
    font-size: clamp(1rem, 3vw, 1.4rem);
    letter-spacing: 6px;
    text-transform: uppercase;
    opacity: 0;
    animation: fadeUp 1s 0.3s forwards;
    margin-bottom: 16px;
  }

  .hero-name {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(3.5rem, 14vw, 9rem);
    color: transparent;
    background: linear-gradient(135deg, #ff6fa8 0%, #ffd700 40%, #ff2d6b 70%, #ffd6e7 100%);
    -webkit-background-clip: text;
    background-clip: text;
    line-height: 1.1;
    opacity: 0;
    animation: fadeUp 1s 0.6s forwards, shimmer 4s 1.5s infinite;
    background-size: 200% auto;
    text-shadow: none;
    filter: drop-shadow(0 0 30px rgba(255,45,107,0.5));
  }

  @keyframes shimmer {
    0%, 100% { background-position: 0% center; }
    50% { background-position: 200% center; }
  }

  .heart-divider {
    font-size: 1.8rem;
    display: flex;
    gap: 12px;
    margin: 16px 0;
    opacity: 0;
    animation: fadeUp 1s 0.9s forwards;
  }
  .heart-divider span { animation: heartbeat 1.2s ease-in-out infinite; }
  .heart-divider span:nth-child(2) { animation-delay: 0.2s; }
  .heart-divider span:nth-child(3) { animation-delay: 0.4s; }

  @keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.3); }
  }

  .nicknames {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
    margin: 20px 0;
    opacity: 0;
    animation: fadeUp 1s 1.1s forwards;
  }

  .nick-tag {
    font-family: 'Dancing Script', cursive;
    font-size: clamp(1rem, 2.5vw, 1.3rem);
    color: var(--white);
    background: linear-gradient(135deg, rgba(255,45,107,0.3), rgba(194,24,91,0.2));
    border: 1px solid rgba(255,107,168,0.4);
    padding: 8px 20px;
    border-radius: 50px;
    backdrop-filter: blur(8px);
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }
  .nick-tag::before {
    content: '';
    position: absolute;
    top: 0; left: -100%;
    width: 100%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
    transition: left 0.5s;
  }
  .nick-tag:hover::before { left: 100%; }
  .nick-tag:hover { transform: translateY(-3px) scale(1.05); border-color: var(--rose); box-shadow: 0 8px 20px rgba(255,45,107,0.3); }

  .birthday-banner {
    font-family: 'Dancing Script', cursive;
    font-size: clamp(1.8rem, 6vw, 3.5rem);
    color: var(--gold);
    text-shadow: 0 0 20px rgba(255,215,0,0.5);
    opacity: 0;
    animation: fadeUp 1s 1.4s forwards;
    margin: 10px 0;
  }

  /* ---- LOVE LETTER SECTION ---- */
  .section {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px;
  }

  .letter-card {
    background: linear-gradient(135deg, rgba(255,45,107,0.08), rgba(30,0,20,0.95));
    border: 1px solid rgba(255,107,168,0.25);
    border-radius: 24px;
    padding: clamp(28px, 6vw, 56px);
    backdrop-filter: blur(16px);
    position: relative;
    overflow: hidden;
    opacity: 0;
    animation: fadeUp 1s 1.8s forwards;
  }

  .letter-card::before {
    content: '❤';
    position: absolute;
    font-size: 300px;
    color: rgba(255,45,107,0.03);
    top: -60px; right: -60px;
    pointer-events: none;
  }

  .letter-title {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(2rem, 6vw, 3.5rem);
    color: var(--rose);
    margin-bottom: 24px;
    text-align: center;
  }

  .letter-body {
    font-size: clamp(1rem, 2.2vw, 1.15rem);
    line-height: 1.95;
    color: rgba(255,230,240,0.9);
    font-style: italic;
    text-align: center;
  }

  .letter-body strong {
    color: var(--pink);
    font-style: normal;
    font-weight: 700;
  }

  /* ---- WISHES GRID ---- */
  .wishes-title {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(2.5rem, 8vw, 5rem);
    color: transparent;
    background: linear-gradient(135deg, var(--rose), var(--gold));
    -webkit-background-clip: text;
    background-clip: text;
    text-align: center;
    margin-bottom: 40px;
    opacity: 0;
    animation: fadeUp 1s 0.2s forwards;
  }

  .wishes-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 20px;
  }

  .wish-card {
    background: linear-gradient(135deg, rgba(255,45,107,0.1), rgba(20,0,12,0.9));
    border: 1px solid rgba(255,107,168,0.2);
    border-radius: 20px;
    padding: 28px 24px;
    text-align: center;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    opacity: 0;
    animation: fadeUp 0.8s forwards;
  }
  .wish-card:nth-child(1) { animation-delay: 0.1s; }
  .wish-card:nth-child(2) { animation-delay: 0.25s; }
  .wish-card:nth-child(3) { animation-delay: 0.4s; }
  .wish-card:nth-child(4) { animation-delay: 0.55s; }
  .wish-card:nth-child(5) { animation-delay: 0.7s; }
  .wish-card:nth-child(6) { animation-delay: 0.85s; }

  .wish-card:hover {
    transform: translateY(-10px) scale(1.03);
    border-color: var(--rose);
    box-shadow: 0 20px 40px rgba(255,45,107,0.25);
    background: linear-gradient(135deg, rgba(255,45,107,0.2), rgba(30,0,20,0.95));
  }

  .wish-icon { font-size: 2.8rem; margin-bottom: 14px; display: block; }
  .wish-card h3 {
    font-family: 'Dancing Script', cursive;
    font-size: 1.4rem;
    color: var(--gold);
    margin-bottom: 10px;
  }
  .wish-card p {
    font-size: 0.95rem;
    color: rgba(255,214,231,0.8);
    line-height: 1.7;
  }

  /* ---- MARQUEE ---- */
  .marquee-wrap {
    position: relative;
    z-index: 1;
    overflow: hidden;
    padding: 20px 0;
    border-top: 1px solid rgba(255,45,107,0.15);
    border-bottom: 1px solid rgba(255,45,107,0.15);
    background: rgba(255,45,107,0.04);
  }

  .marquee-track {
    display: flex;
    gap: 40px;
    width: max-content;
    animation: marquee 18s linear infinite;
  }

  .marquee-track span {
    font-family: 'Dancing Script', cursive;
    font-size: 1.5rem;
    color: var(--rose);
    white-space: nowrap;
    opacity: 0.8;
  }

  @keyframes marquee {
    0% { transform: translateX(0); }
    100% { transform: translateX(-50%); }
  }

  /* ---- FINAL ---- */
  .finale {
    position: relative;
    z-index: 1;
    text-align: center;
    padding: 80px 20px 100px;
  }

  .finale-name {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(4rem, 15vw, 11rem);
    color: transparent;
    background: linear-gradient(135deg, #ffd700, #ff6fa8, #ff2d6b, #ffd700);
    background-size: 300% auto;
    -webkit-background-clip: text;
    background-clip: text;
    animation: shimmer 3s linear infinite;
    filter: drop-shadow(0 0 40px rgba(255,45,107,0.6));
    line-height: 1.1;
  }

  .finale-sub {
    font-family: 'Dancing Script', cursive;
    font-size: clamp(1.2rem, 4vw, 2rem);
    color: rgba(255,214,231,0.8);
    margin-top: 16px;
    letter-spacing: 2px;
  }

  .infinite-love {
    display: inline-block;
    font-size: 4rem;
    margin-top: 30px;
    animation: heartbeat 1s ease-in-out infinite;
  }

  /* ---- UTILS ---- */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes float {
    0%, 100% { transform: translateY(0) rotate(-5deg); }
    50% { transform: translateY(-12px) rotate(5deg); }
  }

  /* Floating names */
  .float-names {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }
  .float-name {
    position: absolute;
    font-family: 'Great Vibes', cursive;
    color: rgba(255,45,107,0.07);
    animation: floatName linear infinite;
    white-space: nowrap;
    user-select: none;
  }
  @keyframes floatName {
    0% { transform: translateY(110vh) rotate(-10deg); opacity: 0; }
    10% { opacity: 1; }
    90% { opacity: 1; }
    100% { transform: translateY(-10vh) rotate(10deg); opacity: 0; }
  }

  /* Responsive */
  @media (max-width: 600px) {
    .letter-card { padding: 28px 18px; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<canvas id="canvas"></canvas>
<div class="float-names" id="floatNames"></div>

<!-- HERO -->
<section class="hero">
  <span class="crown">👑</span>
  <div class="hero-label">✦ A Special Day For A Special Soul ✦</div>
  <div class="hero-name">Musmin Taj</div>

  <div class="heart-divider">
    <span>💖</span><span>💗</span><span>💖</span>
  </div>

  <div class="nicknames">
    <span class="nick-tag">🌸 Taju</span>
    <span class="nick-tag">💞 Meri Jaan</span>
    <span class="nick-tag">🌹 Musu</span>
  </div>

  <div class="birthday-banner">🎂 Happy Birthday, My Love! 🎂</div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track" id="marqueeTrack"></div>
</div>

<!-- LOVE LETTER -->
<div class="section">
  <div class="letter-card">
    <div class="letter-title">A Letter From My Heart</div>
    <p class="letter-body">
      My dearest <strong>Taju</strong>, my <strong>Meri Jaan</strong>, my sweet <strong>Musu</strong> —<br><br>
      On this beautiful day, the universe celebrates the miracle that is <strong>you</strong>.
      Every star in the sky shines a little brighter because you were born.
      Every flower blooms a little sweeter because you exist in this world.<br><br>
      You are my <strong>sunshine on the darkest days</strong>, the melody in every silence,
      the warmth that makes every moment worth living.
      Your smile is my favourite sight, your laugh is my favourite sound,
      and your heart is the most beautiful thing I have ever known.<br><br>
      <strong>Musmin Taj</strong> — today and every day, I am endlessly grateful
      that life brought you to me. You are not just my love — you are my home. 🏡❤️
    </p>
  </div>
</div>

<!-- WISHES GRID -->
<div class="section">
  <div class="wishes-title">My Wishes For You</div>
  <div class="wishes-grid">
    <div class="wish-card">
      <span class="wish-icon">🌟</span>
      <h3>Endless Joy</h3>
      <p>May every single day of your life overflow with laughter, happiness and beautiful surprises.</p>
    </div>
    <div class="wish-card">
      <span class="wish-icon">💐</span>
      <h3>Love Always</h3>
      <p>May you always feel loved, cherished, and celebrated — not just today, but every moment of every day.</p>
    </div>
    <div class="wish-card">
      <span class="wish-icon">✨</span>
      <h3>All Your Dreams</h3>
      <p>May every dream you hold in your precious heart come true, one by one, beautifully.</p>
    </div>
    <div class="wish-card">
      <span class="wish-icon">🍰</span>
      <h3>Sweet Life</h3>
      <p>May life be as sweet as birthday cake, as warm as a hug, and as bright as candles on your cake.</p>
    </div>
    <div class="wish-card">
      <span class="wish-icon">🕊️</span>
      <h3>Perfect Peace</h3>
      <p>May peace and calm always surround you, and may nothing ever disturb your beautiful soul.</p>
    </div>
    <div class="wish-card">
      <span class="wish-icon">💎</span>
      <h3>You Are Rare</h3>
      <p>There is no one like you in the entire world — you are one of a kind, precious beyond words.</p>
    </div>
  </div>
</div>

<!-- SECOND MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track" id="marqueeTrack2"></div>
</div>

<!-- FINALE -->
<section class="finale">
  <div class="finale-name">Musmin Taj</div>
  <div class="finale-sub">Forever & Always, My Queen 👑</div>
  <div class="infinite-love">💖</div>
</section>

<script>
// Custom cursor
const cursor = document.getElementById('cursor');
document.addEventListener('mousemove', e => {
  cursor.style.left = e.clientX + 'px';
  cursor.style.top = e.clientY + 'px';
});

// Marquee content
const marqueeWords = [
  '💖 Happy Birthday Musmin Taj',
  '🌹 I Love You Taju',
  '✨ My Meri Jaan Forever',
  '🎂 Celebrate My Musu',
  '💫 You Are My Everything',
  '🌸 Born To Be Loved',
  '👑 My Queen Always',
];
const repeat = [...marqueeWords, ...marqueeWords, ...marqueeWords];

function fillMarquee(id) {
  const el = document.getElementById(id);
  repeat.forEach(w => {
    const s = document.createElement('span');
    s.textContent = w;
    el.appendChild(s);
  });
}
fillMarquee('marqueeTrack');
fillMarquee('marqueeTrack2');

// Floating background names
const names = ['Musmin Taj', 'Taju', 'Meri Jaan', 'Musu', '❤️', '🌹'];
const floatContainer = document.getElementById('floatNames');
for (let i = 0; i < 18; i++) {
  const el = document.createElement('div');
  el.className = 'float-name';
  el.textContent = names[Math.floor(Math.random() * names.length)];
  el.style.left = Math.random() * 100 + 'vw';
  el.style.fontSize = (1.5 + Math.random() * 4) + 'rem';
  el.style.animationDuration = (12 + Math.random() * 20) + 's';
  el.style.animationDelay = (Math.random() * 15) + 's';
  floatContainer.appendChild(el);
}

// Canvas: hearts, stars, balloons, confetti
const canvas = document.getElementById('canvas');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
window.addEventListener('resize', () => { canvas.width = window.innerWidth; canvas.height = window.innerHeight; });

const COLORS = ['#ff2d6b','#ff6fa8','#ffd700','#ffd6e7','#c2185b','#fff0f7'];
const particles = [];
const TYPES = ['heart','star','circle','balloon'];

class Particle {
  constructor(x, y, fromClick) {
    this.x = x ?? Math.random() * canvas.width;
    this.y = y ?? -20;
    this.type = TYPES[Math.floor(Math.random() * TYPES.length)];
    this.color = COLORS[Math.floor(Math.random() * COLORS.length)];
    this.size = fromClick ? 8 + Math.random() * 12 : 6 + Math.random() * 10;
    this.vx = (Math.random() - 0.5) * (fromClick ? 6 : 1.5);
    this.vy = fromClick ? -5 - Math.random() * 5 : 0.8 + Math.random() * 1.5;
    this.gravity = fromClick ? 0.15 : 0;
    this.alpha = 1;
    this.fade = fromClick ? 0.015 : 0.003;
    this.rotation = Math.random() * Math.PI * 2;
    this.rotSpeed = (Math.random() - 0.5) * 0.08;
    this.fromClick = fromClick;
  }

  draw() {
    ctx.save();
    ctx.globalAlpha = this.alpha;
    ctx.translate(this.x, this.y);
    ctx.rotate(this.rotation);
    ctx.fillStyle = this.color;

    if (this.type === 'heart') {
      const s = this.size * 0.55;
      ctx.beginPath();
      ctx.moveTo(0, s * 0.35);
      ctx.bezierCurveTo(-s, -s * 0.3, -s * 1.5, s * 0.8, 0, s * 1.6);
      ctx.bezierCurveTo(s * 1.5, s * 0.8, s, -s * 0.3, 0, s * 0.35);
      ctx.fill();
    } else if (this.type === 'star') {
      ctx.beginPath();
      for (let i = 0; i < 5; i++) {
        const angle = (i * 4 * Math.PI) / 5 - Math.PI / 2;
        const r = i % 2 === 0 ? this.size : this.size * 0.4;
        ctx.lineTo(Math.cos(angle) * r, Math.sin(angle) * r);
      }
      ctx.closePath(); ctx.fill();
    } else if (this.type === 'balloon') {
      ctx.beginPath();
      ctx.ellipse(0, 0, this.size * 0.7, this.size, 0, 0, Math.PI * 2);
      ctx.fill();
      ctx.beginPath();
      ctx.moveTo(0, this.size);
      ctx.lineTo(2, this.size + 12);
      ctx.strokeStyle = this.color; ctx.globalAlpha = this.alpha * 0.5;
      ctx.lineWidth = 1.2; ctx.stroke();
    } else {
      ctx.beginPath();
      ctx.arc(0, 0, this.size * 0.5, 0, Math.PI * 2);
      ctx.fill();
    }
    ctx.restore();
  }

  update() {
    this.x += this.vx;
    this.vy += this.gravity;
    this.y += this.vy;
    this.rotation += this.rotSpeed;
    this.alpha -= this.fade;
    if (!this.fromClick && this.type === 'balloon') this.vy -= 0.005;
  }

  isDead() { return this.alpha <= 0 || this.y > canvas.height + 30; }
}

// Spawn ambient particles
setInterval(() => {
  if (particles.length < 120) particles.push(new Particle());
}, 120);

// Click burst
document.addEventListener('click', e => {
  for (let i = 0; i < 20; i++) particles.push(new Particle(e.clientX, e.clientY, true));
});

// Pop balloon on hover card
document.querySelectorAll('.wish-card, .nick-tag').forEach(el => {
  el.addEventListener('mouseenter', e => {
    const rect = el.getBoundingClientRect();
    const cx = rect.left + rect.width / 2;
    const cy = rect.top + rect.height / 2;
    for (let i = 0; i < 12; i++) particles.push(new Particle(cx, cy, true));
  });
});

function animate() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  for (let i = particles.length - 1; i >= 0; i--) {
    particles[i].update();
    particles[i].draw();
    if (particles[i].isDead()) particles.splice(i, 1);
  }
  requestAnimationFrame(animate);
}
animate();
</script>
</body>
</html>
