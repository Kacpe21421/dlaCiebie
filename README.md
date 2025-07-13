<html lang="pl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Dla Ciebie ❤️</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Fira+Code&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      height: 100vh;
      width: 100%;
      background: linear-gradient(135deg, #ff69b4, #ff1493);
      overflow: hidden;
      font-family: 'Fira Code', monospace;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    h1 {
      color: white;
      font-size: 2.2rem;
      padding: 1rem;
      text-align: center;
      animation: typing 4s steps(30, end), blink 0.8s step-end infinite;
      white-space: nowrap;
      overflow: hidden;
      border-right: 3px solid white;
      font-family: 'Pacifico', cursive;
      transition: all 0.3s ease-in-out;
    }

    h1:hover {
      color: yellow;
      text-shadow: 0 0 15px #fff, 0 0 30px #f0f, 0 0 60px #ff0;
      transform: scale(1.1);
    }

    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }

    @keyframes blink {
      50% { border-color: transparent }
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 10s linear infinite;
      opacity: 0.7;
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
      top: 0;
      left: -10px;
    }

    canvas.confetti {
      position: fixed;
      top: 0;
      left: 0;
      z-index: 10;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }
  </style>
</head>
<body>
  <h1>Kocham Cię bardzo mocno! ❤️</h1>
  <canvas class="confetti"></canvas>

  <script>
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 5 + 5) + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }

    setInterval(createHeart, 300);

    const canvas = document.querySelector('.confetti');
    const ctx = canvas.getContext('2d');
    let width = canvas.width = window.innerWidth;
    let height = canvas.height = window.innerHeight;

    const confetti = Array.from({ length: 150 }).map(() => ({
      x: Math.random() * width,
      y: Math.random() * height,
      r: Math.random() * 6 + 2,
      d: Math.random() * 10 + 10,
      color: `hsl(${Math.random() * 360}, 100%, 70%)`,
      tilt: Math.random() * 10 - 10,
      tiltAngleIncrement: Math.random() * 0.07 + 0.05,
      tiltAngle: 0
    }));

    function drawConfetti() {
      ctx.clearRect(0, 0, width, height);
      confetti.forEach(p => {
        p.tiltAngle += p.tiltAngleIncrement;
        p.y += (Math.cos(p.d) + 1 + p.r / 2) / 2;
        p.x += Math.sin(0.01);
        p.tilt = Math.sin(p.tiltAngle - (p.r / 3)) * 15;

        ctx.beginPath();
        ctx.lineWidth = p.r;
        ctx.strokeStyle = p.color;
        ctx.moveTo(p.x + p.tilt + p.r / 2, p.y);
        ctx.lineTo(p.x + p.tilt, p.y + p.tilt + p.r / 2);
        ctx.stroke();
      });

      requestAnimationFrame(drawConfetti);
    }

    drawConfetti();

    window.addEventListener('resize', () => {
      width = canvas.width = window.innerWidth;
      height = canvas.height = window.innerHeight;
    });
  </script>

  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/12/01/audio_bdb586728d.mp3?filename=romantic-piano-125997.mp3" type="audio/mpeg">
  </audio>
</body>
</html>

