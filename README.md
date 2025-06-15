<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Футбольне Бізнес Шоу</title>
  <style>
    body {
      background-color: #000;
      background-image: url('stadium_background.jpg');
      background-size: cover;
      color: white;
      font-family: sans-serif;
      padding: 0;
      margin: 0;
    }
    header {
      text-align: center;
      padding: 1rem;
      background: rgba(0,0,0,0.7);
    }
    h1 {
      font-size: 2rem;
    }
    .container {
      padding: 1rem;
      background: rgba(0,0,0,0.7);
    }
    .player, .club {
      display: flex;
      align-items: center;
      margin-bottom: 1rem;
      background: rgba(255,255,255,0.1);
      padding: 0.5rem;
      border-radius: 10px;
    }
    .player img, .club img {
      width: 50px;
      height: 50px;
      margin-right: 1rem;
    }
    audio {
      position: fixed;
      bottom: 10px;
      right: 10px;
    }
  </style>
</head>
<body>
  <header>
    <h1>Футбольне Бізнес Шоу</h1>
    <p>Гра: трансфери, клуби, ліги, змагання</p>
  </header>

  <div class="container">
    <h2>Наші футболісти</h2>
    <div class="player">
      <img src="players/andriy_shevchenko.jpg" alt="Шевченко">
      <div>
        <strong>Андрій Шевченко</strong><br>
        Швидкість: 92 | Удар: 95 | Техніка: 90
      </div>
    </div>
    <div class="player">
      <img src="players/zlatan_ibrahimovic.jpg" alt="Златан">
      <div>
        <strong>Златан Ібрагімович</strong><br>
        Сила: 96 | Удар: 94 | Дриблінг: 88
      </div>
    </div>

    <h2>Українські клуби</h2>
    <div class="club">
      <img src="clubs/dynamo.png" alt="Динамо">
      <div>
        <strong>Динамо Київ</strong><br>
        Бюджет: €40M | Рейтинг: 84 | Фанати: 1.2M
      </div>
    </div>
    <div class="club">
      <img src="clubs/shakhtar.png" alt="Шахтар">
      <div>
        <strong>Шахтар Донецьк</strong><br>
        Бюджет: €45M | Рейтинг: 87 | Фанати: 1.5M
      </div>
    </div>

    <h2>Музичний супровід</h2>
    <audio controls autoplay loop>
      <source src="music/wc2010.mp3" type="audio/mpeg">
      <source src="music/euro2012.mp3" type="audio/mpeg">
      <source src="music/wc2022.mp3" type="audio/mpeg">
      Ваш браузер не підтримує аудіо.
    </audio>

    <h2>Трансфери і сезон</h2>
    <p>Ви можете купувати/продавати гравців між клубами, брати участь у:</p>
    <ul>
      <li>ТОП-5 Ліг Європи (АПЛ, Ла Ліга, Серія А, Бундесліга, Ліга 1)</li>
      <li>Ліга Чемпіонів</li>
      <li>Клубний Чемпіонат Світу</li>
    </ul>
    <button onclick="alert('Починається трансферне вікно!')">Провести трансфери</button>
    <button onclick="alert('Розпочинається сезон!')">Почати сезон</button>
  </div>
</body>
</html>
