<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Você é Incrível!</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #ffe6f0;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
    }

    .message {
      text-align: center;
      z-index: 10;
    }

    .message h1 {
      color: #d63384;
      font-size: 3em;
    }

    .heart {
      position: absolute;
      width: 30px;
      height: 30px;
      background-color: red;
      transform: rotate(45deg);
      animation: floatUp 5s linear infinite;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 30px;
      height: 30px;
      background-color: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -15px;
      left: 0;
    }

    .heart::after {
      left: -15px;
      top: 0;
    }

    @keyframes floatUp {
      0% {
        bottom: -50px;
        left: calc(50% + (100px * (random() - 0.5)));
        opacity: 1;
      }
      100% {
        bottom: 100%;
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <div class="message">
    <h1>Você é incrível!</h1>
  </div>

  <!-- Vários corações animados -->
  <script>
    for (let i = 0; i < 30; i++) {
      let heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
      document.body.appendChild(heart);
    }
  </script>
</body>
</html>
