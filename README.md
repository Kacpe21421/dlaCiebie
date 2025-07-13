
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Dla Ciebie ❤️</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html, body {
      height: 100%;
      font-family: 'Courier New', monospace;
      background: radial-gradient(circle at center, #1a1a1a, #000000);
      overflow: hidden;
      color: white;
    }

    .centered-text {
      position: absolute;
      top: 45%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 6vw;
      text-align: center;
      white-space: nowrap;
      overflow: hidden;
      border-right: 2px solid white;
      width: 0;
      animation: typing 4s steps(40, end) forwards, blink-caret .75s step-end infinite;
    }

    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }

    @keyframes blink-caret {
      from, to { border-color: transparent }
      50% { border-color: white; }
    }

    .heart {
      position: fixed;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: shoot 3s ease-out forwards;
      z-index: 999;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: -10px;
      top: 0;
    }

    .kotek-container {
      position: fixed;
      bottom: 10px;
      left: 10px;
      width: 120px;
      z-index: 99;
    }

    .gif2 {
      position: fixed;
      bottom: 20px;
      right: 10px;
      width: 140px;
      z-index: 99;
    }

    .tenor-gif-embed {
      width: 100%;
    }

    @keyframes background-fade {
      0% { background: radial-gradient(circle at center, #1a1a1a, #000000); }
      50% { background: radial-gradient(circle at center, #ff0077, #1a001a); }
      100% { background: radial-gradient(circle at center, #1a1a1a, #000000); }
    }

    body {
      animation: background-fade 8s infinite ease-in-out;
    }

    @media (max-width: 600px) {
      .centered-text {
        font-size: 8vw;
        top: 40%;
      }
    }
  </style>
</head>
<body>

  <!-- Tekst po środku -->
  <div class="centered-text">
    Kocham Cię bardzo mocno ❤️
  </div>

  <!-- Kot z Tenora -->
  <div class="kotek-container">
    <div class="tenor-gif-embed"
         data-postid="18114953134649251593"
         data-share-method="host"
         data-aspect-ratio="1.01633"
         data-width="100%">
      <a href="https://tenor.com/view/actividades-gif-18114953134649251593">Actividades Sticker</a> from 
      <a href="https://tenor.com/search/actividades-stickers">Actividades Stickers</a>
    </div>
  </div>

  <!-- Twój drugi gif -->
  <img src="actividades (1).gif" alt="gif" class="gif2" />

  <!-- Tenor script -->
  <script type="text/javascript" async src="https://tenor.com/embed.js"></script>

  <!-- Serduszka lecące z kotka -->
  <script>
    function shootHeartFromKotek() {
      const kotekContainer = document.querySelector('.kotek-container');
      const rect = kotekContainer.getBoundingClientRect();
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = (rect.left + rect.width / 2) + 'px';
      heart.style.top = (rect.top + rect.height / 2) + 'px';
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 3000);
    }

    setInterval(shootHeartFromKotek, 700);
  </script>
</body>
</html>





