<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>QR → Play Demo</title>
  <style>
    body { font-family: Arial, sans-serif; display:flex; justify-content:center; align-items:center; min-height:100vh; background:#f4f4f4; margin:0; }
    .card { background:white; padding:32px; border-radius:16px; box-shadow:0 10px 30px rgba(0,0,0,.08); text-align:center; width:360px; }
    button { background:#ff5500; color:white; border:none; padding:12px 20px; border-radius:10px; font-size:16px; cursor:pointer; }
    iframe { margin-top:20px; width:100%; height:166px; border:none; }
    .note { font-size:13px; color:#666; margin-top:12px; }
  </style>
</head>
<body>
  <div class="card">
    <h2>QR → SoundCloud Demo</h2>
    <p>หลังสแกน QR เข้ามาหน้านี้ ระบบจะพยายามเล่นอัตโนมัติ</p>
    <button onclick="playTrack()">▶ Play เพลง</button>
    <iframe id="player" allow="autoplay"></iframe>
    <div class="note">บนมือถือหลายเครื่องอาจยังต้องกดปุ่ม Play เอง</div>
  </div>

  <script>
    const url = 'https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/293&auto_play=true';

    window.onload = () => {
      document.getElementById('player').src = url;
    };

    function playTrack() {
      document.getElementById('player').src = url;
    }
  </script>
</body>
</html>
