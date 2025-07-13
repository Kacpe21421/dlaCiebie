<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Dla Ciebie ❤️</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@500&family=Pacifico&display=swap');

    html, body {
      margin: 0;
      padding: 0;
      background: radial-gradient(circle at center, #ffb6c1, #ff69b4, #ff1493);
      overflow: hidden;
      height: 100%;
      font-family: 'Fira Code', monospace;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    .typewriter {
      font-size: 2.5rem;
      color: white;
      text-align: center;
      white-space: nowrap;
      border-right: 3px solid #fff;
      width: 0;
      overflow: hidden;
      animation: typing 4s steps(30, end), blink 0.75s step-end infinite;
    }

    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }

    @keyframes blink {
      50% { border-color: transparent }
    }

    h1:hover {
      color: #ff0;
      text-shadow: 0 0 20px #fff, 0 0 30px #ff0;
      transition: 0.3s ease-in-out;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 10s infinite ease-in-out;
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
      left: -10px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }

    canvas.confetti {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 100;
    }
  </style>
</head>
<body>

  <div class="typewriter">Kocham Cię bardzo mocno! ❤️</div>
  <canvas class="confetti"></canvas>

  <script>
    // Piszące się serca
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 5 + 5) + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }

    setInterval(createHeart, 200);

    // Konfetti
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
</body>
</html>
