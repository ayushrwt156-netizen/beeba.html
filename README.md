# beeba.htm<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AB Beeba</title>
  <meta name="description" content="AB Beeba — a simple, real website made with love." />
  <style>
    :root {
      --bg1: #ffdde1;
      --bg2: #ee9ca7;
      --card: rgba(255,255,255,0.85);
      --text: #2a2a2a;
      --accent: #e91e63;
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      min-height: 100vh;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, 'Helvetica Neue', Arial, 'Noto Sans', 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';
      color: var(--text);
      background: linear-gradient(135deg, var(--bg1), var(--bg2));
      display: grid;
      place-items: center;
    }
    .card {
      width: min(92vw, 820px);
      background: var(--card);
      border-radius: 20px;
      box-shadow: 0 20px 50px rgba(0,0,0,.15);
      padding: 28px 26px 22px;
      position: relative;
      overflow: hidden;
    }
    .badge {
      position: absolute;
      top: 14px; right: 14px;
      background: #fff;
      color: var(--accent);
      padding: 6px 10px;
      border-radius: 999px;
      font-weight: 700;
      font-size: 12px;
      box-shadow: 0 6px 16px rgba(0,0,0,.12);
    }
    h1 {
      margin: 10px 0 6px;
      font-size: clamp(28px, 4vw, 40px);
      letter-spacing: .3px;
    }
    .subtitle {
      opacity: .85;
      margin-bottom: 18px;
    }
    .hero {
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 18px;
      align-items: center;
    }
    @media (max-width: 720px) {
      .hero { grid-template-columns: 1fr; }
    }
    .message {
      font-size: 16px;
      line-height: 1.6;
      background: #fff;
      border-radius: 16px;
      padding: 16px 16px 14px;
      box-shadow: inset 0 0 0 1px rgba(0,0,0,.04);
    }
    .hearts {
      display: grid;
      place-items: center;
      background: radial-gradient(circle at 30% 30%, #fff, #ffd1dc);
      border-radius: 16px;
      min-height: 200px;
      position: relative;
      overflow: hidden;
    }
    .heart {
      position: absolute;
      width: 18px; height: 18px;
      background: var(--accent);
      transform: rotate(45deg);
      animation: float 6s linear infinite;
      opacity: .85;
    }
    .heart::before, .heart::after {
      content: '';
      position: absolute;
      width: 18px; height: 18px;
      background: var(--accent);
      border-radius: 50%;
      top: -9px; left: 0;
    }
    .heart::after { left: -9px; top: 0; }
    @keyframes float {
      0% { transform: translateY(60px) rotate(45deg); opacity: 0; }
      10% { opacity: .9; }
      100% { transform: translateY(-220px) rotate(45deg); opacity: 0; }
    }
    .controls {
      display: flex; gap: 10px; flex-wrap: wrap; margin-top: 16px;
    }
    .btn {
      border: none;
      background: var(--accent);
      color: #fff;
      padding: 10px 14px;
      border-radius: 999px;
      cursor: pointer;
      font-weight: 700;
      box-shadow: 0 10px 24px rgba(233,30,99,.35);
    }
    .btn.secondary {
      background: #fff;
      color: var(--accent);
      box-shadow: inset 0 0 0 2px var(--accent);
    }
    footer {
      text-align: center;
      margin-top: 18px;
      opacity: .7;
      font-size: 13px;
    }
    .note {
      margin-top: 12px;
      font-size: 13px;
      opacity: .8;
      background: #fff;
      border-radius: 12px;
      padding: 10px 12px;
    }
  </style>
</head>
<body>
  <main class="card">
    <span class="badge">AB Beeba</span>
    <h1>AB Beeba</h1>
    <div class="subtitle">A little corner of the internet made just for you</div>

    <section class="hero">
      <div class="message">
        <p>
          This website is a simple, real page created to celebrate something special.
          It’s soft, warm, and honest — just like the feeling it’s made with.
        </p>
        <p>
          You can keep this page online, share the link, and even add photos or notes anytime.
        </p>
        <div class="controls">
          <button class="btn" onclick="addHeart()">Send a heart</button>
          <button class="btn secondary" onclick="toggleMusic()">Music: On/Off</button>
        </div>
        <div class="note">
          🎵 Background music note: Due to copyright rules, the song can’t be embedded directly.
          Use a legal YouTube embed or your own licensed audio file (instructions below).
        </div>
      </div>
      <div class="hearts" id="hearts">
        <!-- floating hearts appear here -->
      </div>
    </section>

    <!-- OPTIONAL: LEGAL MUSIC EMBED (HOW TO USE)
      1) Get the official YouTube link for the song.
      2) Click Share → Embed → copy the iframe.
      3) Paste it below and set width="0" height="0" so it plays as background (user interaction required by browsers).
      NOTE: Autoplay may require a user click due to browser policies.
    -->
    <!--
    <iframe id="ytMusic" width="0" height="0" src="" title="YouTube audio" allow="autoplay"></iframe>
    -->

    <footer>Made by Ayush</footer>
  </main>

  <script>
    const heartsBox = document.getElementById('hearts');
    function addHeart() {
      const h = document.createElement('div');
      h.className = 'heart';
      h.style.left = Math.random() * 90 + '%';
      h.style.animationDuration = (4 + Math.random() * 4) + 's';
      heartsBox.appendChild(h);
      setTimeout(() => h.remove(), 7000);
    }

    // Music toggle placeholder (works after you add a legal embed)
    let musicOn = false;
    function toggleMusic() {
      musicOn = !musicOn;
      alert('Music toggle ready. Add a legal YouTube embed or licensed audio to enable background music.');
    }
  </script>
</body>
</html>
l
