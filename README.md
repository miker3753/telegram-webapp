<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Кейсы от бота</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Rubik:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Rubik', sans-serif;
      color: #fff;
      background: url('https://i.redd.it/fcv53w4lq2q61.png') center/cover no-repeat fixed;
      backdrop-filter: blur(3px);
    }
    .overlay {
      background-color: rgba(0, 0, 0, 0.65);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 30px;
      text-shadow: 2px 2px #000;
    }
    .case-container {
      display: flex;
      gap: 40px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .case-card {
      background: rgba(255, 255, 255, 0.1);
      border: 2px solid #00ffff;
      border-radius: 16px;
      padding: 20px;
      text-align: center;
      width: 250px;
      transition: transform 0.3s ease;
      box-shadow: 0 4px 20px rgba(0, 255, 255, 0.3);
    }
    .case-card:hover {
      transform: translateY(-5px);
    }
    .case-title {
      font-size: 1.5rem;
      margin-bottom: 10px;
    }
    .case-cost {
      font-size: 1.1rem;
      color: #00ffff;
      margin-bottom: 15px;
    }
    .case-button {
      background-color: #00ffff;
      color: #000;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      font-weight: bold;
      cursor: pointer;
      font-size: 1rem;
      transition: background-color 0.2s;
    }
    .case-button:hover {
      background-color: #00cccc;
    }
    #result {
      margin-top: 40px;
      font-size: 1.6rem;
      color: #00ff88;
      text-shadow: 1px 1px #000;
    }
  </style>
</head>
<body>
  <div class="overlay">
    <h1>🎁 Крути кейс</h1>
    <div class="case-container">
      <div class="case-card">
        <div class="case-title">📖 Кейс с номерами</div>
        <div class="case-cost">10₽</div>
        <button class="case-button" onclick="openCase('numbers')">Открыть</button>
      </div>
      <div class="case-card">
        <div class="case-title">🎁 Telegram подарки</div>
        <div class="case-cost">20₽</div>
        <button class="case-button" onclick="openCase('tg')">Открыть</button>
      </div>
      <div class="case-card">
        <div class="case-title">🎨 NFT-кейс</div>
        <div class="case-cost">50₽</div>
        <button class="case-button" onclick="openCase('nft')">Открыть</button>
      </div>
    </div>
    <div id="result"></div>
  </div>

  <script>
    function openCase(type) {
      const resultEl = document.getElementById("result");
      resultEl.textContent = "Открывается кейс... ⏳";
      setTimeout(() => {
        let prize;
        if (type === "numbers") {
          prize = ["🌟 Бесплатный номер", "Ничего", "10₽", "🔹 20% скидка"];
        } else if (type === "tg") {
          prize = ["💎 Telegram Premium", "Ничего", "💰 30₽", "🎉 Подарок"];
        } else if (type === "nft") {
          prize = ["💼 NFT Pepe", "Пусто", "Вернулось 25₽", "🌟 Супер NFT"];
        }
        const win = prize[Math.floor(Math.random() * prize.length)];
        resultEl.textContent = `Вы выиграли: ${win}`;
      }, 1500);
    }
  </script>
</body>
</html>
