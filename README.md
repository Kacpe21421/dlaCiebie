
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
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
      color: white;
      overflow: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: url('Naszyjnik%20NST2118%20+%20Bransoletka%20BST1512CZ%20(4).gif') no-repeat center center fixed;
      background-size: cover;
      z-index: -1;
    }

    .centered-text {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 2.5rem;
      text-align: center;
      animation: fadeIn 2s ease-in-out;
    }

    @keyframes fadeIn {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }

    .typing {
      border-right: .15em solid white;
      white-space: nowrap;
      overflow: hidden;
      animation: typing 4s steps(40, end), blink-caret .75s step-end infinite;
    }

    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }

    @keyframes blink-caret {
      from, to { border-color: transparent }
      50% { border-color: white; }
    }

    .kotek {
      position: fixed;
      bottom: 10px;
      left: 10px;
      width: 120px;
      z-index: 999;
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

    @keyframes shoot {
      0% {
        opacity: 1;
        transform: translateY(0) scale(1) rotate(45deg);
      }
      100% {
        transform: translateY(-200px) scale(0.5) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="centered-text typing">
    Kocham Cię bardzo mocno ❤️
  </div>

  <!-- Kotek z Tenora -->
  <img src="https://media.tenor.com/Vb-FhRva98sAAAAi/actividades.gif" class="kotek" alt="kotek">

  <script>
    // Tworzenie serduszek z kotka
    const kotek = document.querySelector('.kotek');

    function shootHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      const rect = kotek.getBoundingClientRect();
      heart.style.left = (rect.left + 60) + 'px';
      heart.style.top = (rect.top + 30) + 'px';
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 3000);
    }

    setInterval(shootHeart, 700);
  </script>

</body>
</html>



