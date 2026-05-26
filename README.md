<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>The Morning - SoundCloud Player</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      background: #111;
      color: white;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .container {
      text-align: center;
      width: 100%;
      max-width: 500px;
      padding: 24px;
    }

    h1 {
      font-size: 32px;
      margin-bottom: 10px;
    }

    p {
      opacity: 0.8;
      margin-bottom: 24px;
    }

    button {
      background: #ff5500;
      color: white;
      border: none;
      padding: 16px 28px;
      font-size: 18px;
      border-radius: 14px;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      transform: scale(1.03);
    }

    iframe {
      margin-top: 24px;
      width: 100%;
      height: 166px;
      border: none;
      border-radius: 12px;
    }

    .note {
      margin-top: 14px;
      font-size: 13px;
      opacity: 0.6;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>The Morning</h1>
    <p>Scan QR → Open → Play</p>

    <button onclick="playSong()">▶ Tap to Play</button>

    <iframe
      id="player"
      allow="autoplay"
      src="">
    </iframe>

    <div class="note">
      iPhone / Android บางเครื่องอาจต้องกดปุ่มเอง
    </div>
  </div>

  <script>
    const soundcloudUrl =
      "https://w.soundcloud.com/player/?url=https%3A//soundcloud.com/dhy-na/the-morning&auto_play=true&hide_related=false&show_comments=false&show_user=true&show_reposts=false&visual=true";

    const player = document.getElementById("player");

    // พยายาม autoplay ตอนเข้าเว็บ
    window.onload = () => {
      player.src = soundcloudUrl;
    };

    // fallback ถ้า browser บล็อก
    function playSong() {
      player.src = "";
      setTimeout(() => {
        player.src = soundcloudUrl;
      }, 100);
    }
  </script>

</body>
</html>
