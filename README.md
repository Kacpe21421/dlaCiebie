
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Na Zawsze ❤️</title>

  <style>
    @import url('https://fonts.googleapis.com/css2?family=Sacramento&family=Inter:wght@400;700&display=swap');

    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
      background: linear-gradient(135deg, #000000, #000000);
      background-repeat: no-repeat;
      background-attachment: fixed;
      font-family: 'Inter', sans-serif;
      overflow-x: hidden;
    }

    body {
      color: #fff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    h1 {
      font-family: 'Sacramento', cursive;
      font-size: 4rem;
      color: #fff;
      text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
      animation: fadeInDown 2s ease-out;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.3rem;
      color: #fff;
      max-width: 600px;
      text-shadow: 0 1px 3px rgba(0,0,0,0.4);
      animation: fadeInUp 3s ease-out;
      margin-bottom: 30px;
    }

    @keyframes fadeInDown {
      0% { opacity: 0; transform: translateY(-50px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInUp {
      0% { opacity: 0; transform: translateY(50px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .accordion-container {
  width: 90%;
  max-width: 600px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.accordion-toggle {
  width: 100%;
  padding: 15px 20px;
  font-size: 1.2rem;
  background: #fff;
  color: #d94f70;
  border: none;
  border-radius: 12px;
  cursor: pointer;
  font-weight: bold;
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
  transition: background 0.3s ease;
  text-align: center;
}

.accordion-toggle:hover {
  background: #ffe4ec;
}

.accordion-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.5s ease;
  background: rgba(255, 255, 255, 0.2);
  border-bottom-left-radius: 12px;
  border-bottom-right-radius: 12px;
  margin-top: -2px;
  padding: 0 20px;
  width: 100%;
}

    .accordion-content ul {
      list-style: none;
      padding: 15px 0;
      margin: 0;
      color: #fff;
      text-shadow: 0 1px 5px rgba(0,0,0,0.3);
      font-size: 0.95rem;
      line-height: 1.5;
    }

    .accordion-content li {
      margin-bottom: 10px;
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
  <h1>Kocham Cię bardzo ❤️</h1>
  <p>Jesteś moją najważniejszą osobą. Cieszę się, że jesteś. Ta strona to tylko mały ułamek tego, co dla mnie znaczysz.</p>

  <div class="accordion-container">
    <button class="accordion-toggle">Dlaczego Cię kocham? 💖</button>
    <div class="accordion-content">
      <ul>
        <li>Bo zawsze potrafisz mnie rozśmieszyć nawet w najgorszy dzień.</li>
        <li>Bo jesteś najczulszą i najpiękniejszą duszą, jaką spotkałem.</li>
        <li>Bo przy Tobie wszystko ma sens – nawet zwykła cisza.</li>
        <li>Bo potrafisz kochać tak, jak nikt inny na tym świecie.</li>
        <li>Bo jesteś po prostu Ty – i to wystarczy. 🥺</li>
      </ul>
    </div>
  </div>

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

    // Akordeon
    document.querySelector('.accordion-toggle').addEventListener('click', () => {
      const content = document.querySelector('.accordion-content');
      content.style.maxHeight = content.style.maxHeight ? null : content.scrollHeight + 'px';
    });
  </script>

  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_e487f8ba46.mp3" type="audio/mpeg">
  </audio>
</body>
</html>

