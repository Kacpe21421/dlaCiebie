<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dla Ciebie ❤️</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
      background: linear-gradient(-45deg, #ff4b91, #ff6ec4, #ff85a1, #ffb6c1);
      background-size: 400% 400%;
      animation: backgroundAnimation 10s ease infinite;
      font-family: 'Pacifico', cursive;
      overflow: hidden;
    }

    @keyframes backgroundAnimation {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    h1 {
      font-size: 4rem;
      color: white;
      text-align: center;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-shadow: 0 0 20px #ff1493, 0 0 40px #ff69b4;
      animation: pulse 2s infinite, glowText 3s infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: translate(-50%, -50%) scale(1); }
      50% { transform: translate(-50%, -50%) scale(1.1); }
    }

    @keyframes glowText {
      0% { text-shadow: 0 0 10px #ff69b4; }
      50% { text-shadow: 0 0 30px #ff1493, 0 0 50px #ff69b4; }
      100% { text-shadow: 0 0 10px #ff69b4; }
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 8s linear infinite;
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

    .heart::before { top: -10px; left: 0; }
    .heart::after { left: -10px; top: 0; }

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

    .confetti {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 99;
    }
  </style>
</head>
<body>
  <h1>Kocham Cię bardzo mocno! ❤️</h1>
  <canvas class="confetti"></canvas>

  <script>
    // Serduszka
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 3 + 5) + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }
    setInterval(createHeart, 200);

    // Konfetti
    const canvas = document.querySelector('.confetti');
    const ctx = canvas.getContext('2d');
    let w = canvas.width = window.innerWidth;
    let h = canvas.height = window.innerHeight;

    const confetti = Array.from({ length: 150 }).map(() => ({
      x: Math.random() * w,
      y: Math.random() * h,
      r: Math.random() * 6 + 2,
      d: Math.random() * 10 + 10,
      color: `hsl(${Math.random() * 360}, 100%, 75%)`,
      tilt: Math.random() * 10 - 10,
      tiltAngleIncrement: Math.random() * 0.07 + 0.05,
      tiltAngle: 0
    }));

    function drawConfetti() {
      ctx.clearRect(0, 0, w, h);
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
      w = canvas.width = window.innerWidth;
      h = canvas.height = window.innerHeight;
    });
  </script>
</body>
</html>
