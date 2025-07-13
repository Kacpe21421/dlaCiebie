
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
  </style>
</head>
<body>

  <div class="centered-text typing">
    Kocham Cię bardzo mocno ❤️
  </div>

</body>
</html>



