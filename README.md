<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Футбол Бізнес Шоу</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f0f5;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #222;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #333;
      padding: 10px;
      text-align: center;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    main {
      padding: 20px;
    }
    .section {
      margin-bottom: 40px;
    }
    .game-board {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      gap: 10px;
      margin: 20px auto;
      max-width: 600px;
    }
    .cell {
      background-color: #fff;
      border: 2px solid #444;
      padding: 20px;
      text-align: center;
      font-weight: bold;
    }
    .controls {
      text-align: center;
      margin: 30px 0;
    }
    .status {
      text-align: center;
      font-size: 1.2em;
      margin-bottom: 20px;
    }
    button {
      padding: 10px 20px;
      font-size: 1em;
      cursor: pointer;
    }
    table {
      width: 100%;
      border-collapse: collapse;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 8px;
      text-align: center;
    }
    th {
      background-color: #ddd;
    }
  </style>
</head>
<body>
  <header>
    <h1>Футбол Бізнес Шоу</h1>
    <p>Стань футбольним магнатом!</p>
  </header>
  <nav>
    <a href="#game">Грати</a>
    <a href="#clubs">ТОП-50 клубів</a>
    <a href="#players">ТОП-100 футболістів</a>
    <a href="#stats">Рейтинги</a>
    <a href="#save">Збереження</a>
  </nav>
  <main>
    <div class="section" id="game">
      <div class="status">
        Баланс: <span id="balance">1000000</span> ₴<br>
        Поточна позиція: <span id="position">0</span>
      </div>
      <div class="controls">
        <button onclick="rollDice()">Кинути кубик</button>
        <button onclick="saveResult()">Зберегти результат</button>
      </div>
      <div class="game-board" id="gameBoard"></div>
    </div>

    <div class="section" id="clubs">
      <h2>ТОП-50 футбольних клубів</h2>
      <table>
        <tr><th>Клуб</th><th>Рейтинг</th><th>Фанати (млн)</th><th>Бюджет (€)</th></tr>
        <tr><td>Реал Мадрид</td><td>95</td><td>500</td><td>1.2B</td></tr>
        <tr><td>Манчестер Сіті</td><td>94</td><td>450</td><td>1.0B</td></tr>
        <tr><td>Барселона</td><td>93</td><td>470</td><td>900M</td></tr>
        <tr><td>Баварія</td><td>92</td><td>380</td><td>950M</td></tr>
        <tr><td>Шахтар</td><td>84</td><td>40</td><td>100M</td></tr>
        <tr><td>Динамо Київ</td><td>82</td><td>35</td><td>70M</td></tr>
        <!-- Додати ще 44 клуби... -->
      </table>
    </div>

    <div class="section" id="players">
      <h2>ТОП-100 футболістів світу + Легенди</h2>
      <table>
        <tr><th>Гравець</th><th>Клуб</th><th>Рейтинг</th></tr>
        <tr><td>Кіліан Мбаппе</td><td>Реал Мадрид</td><td>93</td></tr>
        <tr><td>Ерлінг Голанд</td><td>Манчестер Сіті</td><td>92</td></tr>
        <tr><td>Ліонель Мессі</td><td>Інтер Маямі</td><td>91</td></tr>
        <tr><td>Златан Ібрагімович</td><td>Легенда</td><td>89</td></tr>
        <tr><td>Андрій Шевченко</td><td>Україна (легенда)</td><td>90</td></tr>
        <tr><td>Сергій Ребров</td><td>Україна (легенда)</td><td>88</td></tr>
        <tr><td>Андрій Ярмоленко</td><td>Динамо Київ</td><td>80</td></tr>
        <!-- Додати ще 93 гравці... -->
      </table>
    </div>

    <div class="section" id="stats">
      <h2>Активи та рейтинги</h2>
      <p><strong>Клубні активи:</strong> стадіон, академія, ТВ-права</p>
      <p><strong>Фанати:</strong> впливають на дохід</p>
      <p><strong>Рейтинг клубу:</strong> впливає на перемоги у матчах</p>
      <p><strong>Рейтинг гравця:</strong> покращує ефект трансферів</p>
    </div>

    <div class="section" id="save">
      <h2>Програма гри і збереження</h2>
      <p>Після кожного ходу натисни "Зберегти результат". Дані зберігаються у браузері. Пізніше можна додати вивантаження в Google Sheets або на сервер.</p>
    </div>
  </main>

  <script>
    const sectors = [
      "СТАРТ",
      "Матч – +300000 ₴",
      "Трансфер – -500000 ₴",
      "Шоу – +200000 ₴",
      "Фанати – +/-100000 ₴",
      "Штраф – -200000 ₴",
      "Реклама – +150000 ₴",
      "Матч",
      "Скандал – -300000 ₴",
      "Медіа – +250000 ₴",
      "Стадіон – -600000 ₴",
      "Фанати",
      "? – випадкова подія",
      "Матч",
      "Шоу",
      "Трансфер",
      "?",
      "Реклама",
      "Штраф",
      "Матч",
      "Скандал",
      "Фанати",
      "Шоу",
      "ФІНІШ"
    ];

    let balance = 1000000;
    let position = 0;

    function updateBoard() {
      const board = document.getElementById("gameBoard");
      board.innerHTML = "";
      sectors.forEach((sector, index) => {
        const cell = document.createElement("div");
        cell.className = "cell";
        cell.textContent = sector;
        if (index === position) {
          cell.style.backgroundColor = "#ffe066";
        }
        board.appendChild(cell);
      });
      document.getElementById("balance").textContent = balance;
      document.getElementById("position").textContent = position;
    }

    function rollDice() {
      const roll = Math.floor(Math.random() * 6) + 1;
      position = (position + roll) % sectors.length;
      applySectorEffect(sectors[position]);
      updateBoard();
    }

    function applySectorEffect(sector) {
      if (sector.includes("+")) {
        const amount = parseInt(sector.match(/\+(\d+)/)?.[1] || 0);
        balance += amount;
      }
      if (sector.includes("-")) {
        const amount = parseInt(sector.match(/-(\d+)/)?.[1] || 0);
        balance -= amount;
      }
    }

    function saveResult() {
      const gameData = {
        balance,
        position,
        date: new Date().toLocaleString()
      };
      localStorage.setItem("footballGameSave", JSON.stringify(gameData));
      alert("Результат збережено!");
    }

    updateBoard();
  </script>
</body>
</html>
