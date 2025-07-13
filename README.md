
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Dla Ciebie ❤️</title>
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      height: 100vh;
      background: linear-gradient(135deg, #ffafbd, #ffc3a0);
      font-family: 'Dancing Script', cursive;
      overflow: hidden;
      position: relative;
      animation: backgroundFade 10s infinite alternate;
    }

    @keyframes backgroundFade {
      0% { background: linear-gradient(135deg, #ffafbd, #ffc3a0); }
      50% { background: linear-gradient(135deg, #ffc3a0, #ffafbd); }
      100% { background: linear-gradient(135deg, #ffafbd, #ffc3a0); }
    }

    .typing-text {
      position: absolute;
      top: 40%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 8vw;
      color: white;
      text-shadow: 2px 2px 10px #ff4081;
      white-space: nowrap;
      overflow: hidden;
      border-right: 3px solid white;
      width: 0;
      animation: typing 4s steps(40, end) forwards, blink-caret 0.75s step-end infinite;
    }

    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }

    @keyframes blink-caret {
      from, to { border-color: transparent; }
      50% { border-color: white; }
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: red;
      transform: rotate(45deg);
      animation: float 6s linear infinite;
      opacity: 0.8;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: red;
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

    @keyframes float {
      0% {
        transform: translateY(0) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-120vh) rotate(45deg);
        opacity: 0;
      }
    }

    @media (max-width: 600px) {
      .typing-text {
        font-size: 10vw;
      }
    }
  </style>
</head>
<body>

  <div class="typing-text">Kocham Cię bardzo mocno ❤️</div>

  <script>
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 2 + 4) + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }

    setInterval(createHeart, 300);
  </script>
</body>
</html>




