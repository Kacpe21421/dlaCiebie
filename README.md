<html lang="pl">
<head>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Sacramento&family=Inter:wght@400;700&display=swap');

    body {
      margin: 0;
      padding: 0;
      background: url('https://i.imgur.com/B3ZQjGt.jpg') center center / cover no-repeat fixed;
      font-family: 'Inter', sans-serif;
      color: #fff;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      overflow: hidden;
      text-align: center;
    }

    h1, h2 {
      font-family: 'Sacramento', cursive;
      font-size: 4rem;
      margin: 10px 0;
      text-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
      animation: fadeInDown 2s ease-out;
    }

    h2 {
      font-size: 3rem;
      animation: fadeInUp 3s ease-out;
    }

    p {
      font-size: 1.2rem;
      max-width: 600px;
      text-align: center;
      animation: fadeInUp 3s ease-out;
      color: #fefefe;
      text-shadow: 0 1px 5px rgba(0, 0, 0, 0.3);
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

    .confetti {
      position: fixed;
      width: 10px;
      height: 10px;
      background-color: red;
      animation: confettiFall 3s linear forwards;
      opacity: 0.9;
      border-radius: 50%;
      z-index: 9999;
    }

    @keyframes confettiFall {
      0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
      100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <h2>Dla Ciebie 🐾</h2>
  <h1>Kocham Cię bardzo ❤️</h1>
  <p>Jesteś moją najważniejszą osobą. Cieszę się, że jesteś. Ta strona to tylko mały ułamek tego, co dla mnie znaczysz.</p>

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

    function launchConfetti() {
      for (let i = 0; i < 100; i++) {
        const confetti = document.createElement('div');
        confetti.classList.add('confetti');
        confetti.style.left = Math.random() * 100 + 'vw';
        confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 70%)`;
        confetti.style.width = `${5 + Math.random() * 5}px`;
        confetti.style.height = `${5 + Math.random() * 5}px`;
        confetti.style.animationDuration = `${2 + Math.random() * 2}s`;
        document.body.appendChild(confetti);
        setTimeout(() => confetti.remove(), 4000);
      }
    }

    window.onload = launchConfetti;
  </script>

  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_e487f8ba46.mp3" type="audio/mpeg">
  </audio>
</body>
</html>




