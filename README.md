
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

    body, html {
      height: 100%;
      font-family: 'Courier New', monospace;
      color: white;
      overflow: hidden;
    }

    video#bg-video {
      position: fixed;
      right: 0;
      bottom: 0;
      min-width: 100%;
      min-height: 100%;
      object-fit: cover;
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
  </style>
</head>
<body>

  <video autoplay muted loop id="bg-video">
    <source src="9905539-hd_1920_1080_30fps.mp4" type="video/mp4">
    Twój przeglądarka nie obsługuje wideo 😢
  </video>

  <div class="centered-text typing">
    Kocham Cię bardzo mocno ❤️
  </div>

</body>
</html>


