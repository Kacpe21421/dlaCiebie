
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Dla Ciebie ❤️</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Sacramento&family=Inter:wght@400;700&display=swap');

    body {
      margin: 0;
      padding: 0;
      background: radial-gradient(circle at center, #ffdde1, #ee9ca7);
      font-family: 'Inter', sans-serif;
      color: #333;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      overflow: hidden;
    }

    h1 {
      font-family: 'Sacramento', cursive;
      font-size: 4rem;
      color: #fff;
      text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
      margin-bottom: 20px;
      animation: fadeInDown 2s ease-out;
    }

    p {
      font-size: 1.3rem;
      color: #fff;
      max-width: 600px;
      text-align: center;
      animation: fadeInUp 3s ease-out;
    }

    @keyframes fadeInDown {
      0% { opacity: 0; transform: translateY(-50px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInUp {
      0% { opacity: 0; transform: translateY(50px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .heart {
      position: absolute;
      width: 15px;
      height: 15px;
      background: red;
      transform: rotate(45deg);
      animation: floatUp 10s linear infinite;
      opacity: 0.6;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 15px;
      height: 15px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -7.5px;
      left: 0;
    }

    .heart::after {
      left: -7.5px;
      top: 0;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 0;
      }
      20% { opacity: 0.6; }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <h1>Dla Ciebie, Skarbie ❤️</h1>
  <p>W całym internecie, na całym świecie – tylko Ty jesteś moim wszechświatem.</p>

  <script>
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (6 + Math.random() * 4) + 's';
      heart.style.opacity = Math.random();
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }

    setInterval(createHeart, 300);
  </script>

  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_e487f8ba46.mp3" type="audio/mpeg">
  </audio>
</body>
</html>





