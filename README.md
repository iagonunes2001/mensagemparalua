<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Te Amo Todo Dia</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Arial', sans-serif;
      color: #333;
      overflow: hidden;
    }
    .container {
      text-align: center;
      background: rgba(255, 255, 255, 0.9);
      padding: 40px;
      border-radius: 15px;
      box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
      max-width: 500px;
    }
    h1 {
      font-size: 2.5em;
      color: #e91e63;
      margin-bottom: 20px;
    }
    p {
      font-size: 1.2em;
      line-height: 1.5;
      margin: 10px 0;
    }
    #days {
      font-size: 3em;
      color: #d81b60;
      font-weight: bold;
      margin: 20px 0;
    }
    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: #e91e63;
      transform: rotate(-45deg);
      animation: float 6s infinite;
    }
    .heart::before,
    .heart::after {
      content: '';
      width: 20px;
      height: 20px;
      background: #e91e63;
      border-radius: 50%;
      position: absolute;
    }
    .heart::before {
      top: -10px;
      left: 0;
    }
    .heart::after {
      left: 10px;
      top: 0;
    }
    @keyframes float {
      0% { transform: translateY(0) rotate(-45deg); opacity: 1; }
      100% { transform: translateY(-100vh) rotate(-45deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Te Amo, Cabeçuda! ❤️</h1>
    <p>Já faz <span id="days">0</span> dias que amo você, meu bichinho.</p>
    <p>Cada dia com você é uma nova razão para sorrir. Te amo hoje e sempre!</p>
  </div>
  <script>
    function calculateDays() {
      const startDate = new Date('2024-08-02'); // Data que vocês começaram a se amar
      const today = new Date();
      const diffTime = Math.abs(today - startDate);
      const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));
      document.getElementById('days').textContent = diffDays;
    }

    function createHearts() {
      setInterval(() => {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = Math.random() * 3 + 3 + 's';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 6000);
      }, 500);
    }

    calculateDays();
    createHearts();
  </script>
</body>
</html>
