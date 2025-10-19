<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Chúc mừng 20/10</title>
  <style>
    :root {
      --accent: #e85a70;
      --text: #fff9f9;
      --bg: #d48b91; /* màu nền mới */
      --sub: #b23a48;
    }
    html, body {
      height: 100%;
      margin: 0;
      font-family: 'Poppins', system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif;
      overflow: hidden; /* ẩn thanh trượt cả ngang và dọc */
    }
    body {
      background: #d48b91; /* chỉ 1 màu nền */
      color: var(--text);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
    }
    .card {
      width: min(980px, 94vw);
      box-sizing: border-box;
      background: rgba(255, 255, 255, 0.15);
      backdrop-filter: blur(4px);
      border-radius: 20px;
      padding: 36px 28px;
      text-align: center;
      margin-top: 60px;
      box-shadow: none;
      border: none;
    }
    h1 {
      font-size: 64px;
      margin: 0 0 20px 0;
      color: var(--sub);
      letter-spacing: 1px;
      text-shadow: 2px 2px 8px rgba(0,0,0,0.15);
    }
    p.lead {
      margin: 0 0 20px 0;
      font-size: 24px;
      color: var(--text);
    }

    .blink-white { animation: blink 1.5s infinite; }
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.6; } }

    .heart {
      position: absolute;
      top: -10%;
      color: #ffccd5;
      font-size: 20px;
      opacity: 0.9;
      animation: fall linear forwards;
    }
    @keyframes fall {
      0% { transform: translateY(-20vh) rotate(0) translateX(0); opacity: 1; }
      100% { transform: translateY(120vh) rotate(360deg) translateX(120px); opacity: 0; }
    }

    .love-section {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      margin-top: 40px;
      color: #b23a48;
      font-family: 'Poppins', sans-serif;
      border: none;
    }
    .love-section h2 {
      font-size: 3rem;
      font-weight: 600;
      letter-spacing: 3px;
      margin-bottom: 10px;
      color: #b23a48;
      text-shadow: 1px 1px 8px rgba(0,0,0,0.1);
    }
    .line {
      width: 180px;
      height: 3px;
      background: #fff;
      margin-top: 10px;
      position: relative;
      overflow: hidden;
      border-radius: 2px;
      border: none;
    }
    .line::before {
      content: "";
      position: absolute;
      width: 60px;
      height: 3px;
      background: var(--sub);
      left: -60px;
      animation: moveLine 2s linear infinite;
    }
    @keyframes moveLine { 0% { left: -60px; } 100% { left: 180px; } }

    .mini-heart {
      position: absolute;
      width: 10px; height: 10px;
      background: #ff758f;
      transform: rotate(45deg);
      animation: fly 3s linear infinite;
    }
    .mini-heart::before, .mini-heart::after {
      content: "";
      position: absolute;
      width: 10px; height: 10px;
      background: #ff758f;
      border-radius: 50%;
    }
    .mini-heart::before { top: -5px; left: 0; }
    .mini-heart::after { left: 5px; top: 0; }
    @keyframes fly { 0% { transform: translateY(0) rotate(45deg); opacity: 1; } 100% { transform: translateY(-150px) rotate(45deg); opacity: 0; } }

    #music-toggle {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: linear-gradient(45deg, #b23a48, #e85a70);
      color: #fff;
      border: none;
      border-radius: 25px;
      padding: 10px 16px;
      cursor: pointer;
      font-size: 18px;
      font-weight: bold;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
      transition: all 0.3s ease;
    }
    #music-toggle:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 16px rgba(0,0,0,0.25);
    }

    @media (max-width:520px){
      h1 { font-size:46px }
      .card { padding:20px; padding-top:40px }
      p.lead { font-size:20px }
    }
  </style>
</head>
<body>
  <div class="card" id="card">
    <h1>Chúc mừng 20/10</h1>
    <p class="lead blink-white">
      Thay mặt toàn thể các bạn nam trong lớp chúng tớ xin chúc các bạn nữ và cô giáo của chúng em một ngày 20/10 tràn ngập niềm vui, hạnh phúc và ý nghĩa. Chúng tớ mong các cậu cũng như là cô giáo luôn đồng hành cùng chúng tớ trên quãng đường còn lại! 🌹 ❤️
    </p>
  </div>

  <div class="love-section" id="love">
    <h2>I LOVE YOU</h2>
    <div class="line"></div>
    <div class="mini-heart" style="left:48%; animation-delay:0s;"></div>
    <div class="mini-heart" style="left:52%; animation-delay:0.5s;"></div>
    <div class="mini-heart" style="left:56%; animation-delay:1s;"></div>
  </div>

  <audio id="bg-music" src="nhac.mp3" loop></audio>
  <button id="music-toggle">🔊</button>

  <script>
    const music = document.getElementById('bg-music');
    const toggleBtn = document.getElementById('music-toggle');
    const love = document.getElementById('love');
    let playing = false;
    let loveShown = false;

    toggleBtn.addEventListener('click', ()=>{
      if(!playing){
        music.play();
        playing = true;
        toggleBtn.textContent = '🔇';
        if(!loveShown){
          love.style.display = 'flex';
          loveShown = true;
        }
      } else {
        music.pause();
        playing = false;
        toggleBtn.textContent = '🔊';
      }
    });

    function makeHeart(){
      const h = document.createElement('div');
      h.className = 'heart';
      h.textContent = '❤';
      const size = Math.random()*16 + 14;
      h.style.fontSize = size+'px';
      h.style.left = Math.random()*100+'%';
      h.style.top = (Math.random()*-20)+'%';
      h.style.opacity = (0.6 + Math.random()*0.4);
      const dur = 6 + Math.random()*8;
      h.style.animationDuration = dur+'s';
      document.body.appendChild(h);
      setTimeout(()=>h.remove(), (dur+1)*1000);
    }
    setInterval(makeHeart, 600);
  </script>
</body>
</html>
