# meu-site-romantico
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>S2 Te amo ❤️</title>
  <style>
    :root {
      --accent: #ff4d4d;
      --bg1: #fff0f5;
      --bg2: #ffe6e6;
      --text: #b30000;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: linear-gradient(135deg, var(--bg1), var(--bg2));
      color: var(--text);
      font-family: "Poppins", sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      text-align: center;
    }

    header {
      margin-bottom: 40px;
      animation: fadeIn 2s ease-in-out;
    }

    h1 {
      font-size: 2.5rem;
      color: var(--accent);
      text-shadow: 2px 2px 6px rgba(255, 0, 0, 0.3);
    }

    .heart {
      display: inline-block;
      animation: pulse 1s infinite;
    }

    /* Caixa principal */
    #output {
      display: inline-block;
      padding: 40px 80px;
      font-size: 2rem;
      background-color: rgba(255, 255, 255, 0.8);
      border-radius: 30px;
      box-shadow: 0 10px 25px rgba(255, 0, 0, 0.3);
      animation: fadeInUp 2s ease;
      z-index: 2;
      font-weight: bold;
      margin-bottom: 25px;
    }

    /* Caixa de texto horizontal */
    .love-box {
      margin-top: 20px;
      padding: 20px 30px;
      background: rgba(255, 255, 255, 0.7);
      border: 3px solid var(--accent);
      border-radius: 20px;
      box-shadow: 0 6px 15px rgba(255, 0, 0, 0.25);
      font-size: 1.4rem;
      font-weight: 500;
      color: var(--text);
      max-width: 700px;
      white-space: nowrap; /* Mantém o texto em uma linha */
      overflow: hidden;
      text-overflow: ellipsis;
      animation: fadeInUp 2s ease;
    }

    footer {
      margin-top: 20px;
      font-size: 0.9rem;
      opacity: 0.8;
      color: #444;
    }

    /* Botão elegante */
    .music-btn {
      margin-top: 30px;
      background: var(--accent);
      color: white;
      border: none;
      padding: 14px 28px;
      border-radius: 40px;
      cursor: pointer;
      font-size: 1.1rem;
      font-weight: bold;
      box-shadow: 0 8px 15px rgba(255, 0, 0, 0.3);
      transition: all 0.3s ease;
      animation: fadeInUp 2s ease;
    }

    .music-btn:hover {
      background-color: #ff1a1a;
      transform: scale(1.08);
      box-shadow: 0 10px 20px rgba(255, 0, 0, 0.4);
    }

    /* Animações */
    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.15); }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* Corações caindo */
    .falling-heart {
      position: fixed;
      top: -50px;
      font-size: 24px;
      color: var(--accent);
      animation: fall linear forwards;
      z-index: 1;
    }

    @keyframes fall {
      to {
        transform: translateY(110vh);
        opacity: 0;
      }
    }

    /* Player do SoundCloud */
    .soundcloud-player {
      margin-top: 20px;
      display: none;
      animation: fadeIn 1s ease-in-out;
    }

  </style>
</head>
<body>
  <header>
    <h1><span class="heart">❤️ S2 Te amo &lt;3 ❤️</span></h1>
  </header>

  <div id="output">S2 Te amo &lt;3</div>

  <!-- Caixa de texto -->
  <div class="love-box">Minha vida só faz sentido se você estiver ao meu lado.</div>

  <!-- Botão elegante -->
  <button class="music-btn" id="musicBtn">🎵 Tocar música</button>

  <!-- Player do SoundCloud -->
  <div class="soundcloud-player" id="soundcloudPlayer">
    <iframe 
      width="100%" 
      height="166" 
      scrolling="no" 
      frameborder="no" 
      allow="autoplay" 
      src="https://w.soundcloud.com/player/?url=https%3A//soundcloud.com/gmzfdnn/george-michael-careless&color=%23ff4d4d&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true">
    </iframe>
  </div>

  <footer>Feito com 💖 e HTML — Versão 5.0</footer>

  <script>
    // Corações caindo
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("falling-heart");
      heart.textContent = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = Math.random() * 3 + 3 + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }
    setInterval(createHeart, 200);

    // Mostrar/ocultar player do SoundCloud
    const btn = document.getElementById("musicBtn");
    const player = document.getElementById("soundcloudPlayer");
    let visible = false;

    btn.addEventListener("click", () => {
      visible = !visible;
      if (visible) {
        player.style.display = "block";
        btn.textContent = "⏸️ Ocultar música";
      } else {
        player.style.display = "none";
        btn.textContent = "🎵 Tocar música";
      }
    });
  </script>
</body>
</html>
