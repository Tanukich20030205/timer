<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>25分タイマー</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      padding: 2em;
    }
    h1 {
      font-size: 48px;
      margin-bottom: 20px;
    }
    button {
      font-size: 20px;
      padding: 10px 20px;
    }
  </style>
</head>
<body>
  <h1 id="timer">25:00</h1>
  <button onclick="startTimer()">スタート</button>

  <script>
    let duration = 25 * 60; // 25分
    let timer;
    function startTimer() {
      let time = duration;
      const display = document.getElementById('timer');
      clearInterval(timer);
      timer = setInterval(() => {
        const minutes = Math.floor(time / 60);
        const seconds = time % 60;
        display.textContent =
          String(minutes).padStart(2, '0') + ":" + String(seconds).padStart(2, '0');
        if (--time < 0) {
          clearInterval(timer);
          alert("25分経過しました！");
        }
      }, 1000);
    }
  </script>
</body>
</html>
