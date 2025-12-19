# Mine<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>I Love You Infinity 💙♾️💗</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      height: 100vh;
      background: url('https://images.unsplash.com/photo-1501004318641-b39e6451bec6') no-repeat center center/cover;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      color: white;
    }

    .container {
      background: rgba(0, 0, 0, 0.55);
      padding: 30px;
      border-radius: 20px;
      max-width: 90%;
    }

    h1 {
      font-size: 2.2rem;
      margin-bottom: 20px;
    }

    button {
      padding: 12px 25px;
      font-size: 1rem;
      border: none;
      border-radius: 30px;
      background: linear-gradient(45deg, #ff5fa2, #ff85c2);
      color: white;
      cursor: pointer;
      transition: transform 0.2s ease;
    }

    button:hover {
      transform: scale(1.05);
    }

    .hidden {
      display: none;
      margin-top: 25px;
    }

    img {
      max-width: 100%;
      border-radius: 15px;
      margin-top: 15px;
    }

    .love-text {
      font-size: 1.5rem;
      margin-top: 15px;
      color: #ffb6d9;
    }
    .heart {
      position: fixed;
      bottom: -10px;
      font-size: 20px;
      animation: floatUp 6s linear infinite;
      opacity: 0.8;
    }

    @keyframes floatUp {
      0% { transform: translateY(0) rotate(0deg) scale(1); opacity: 1; }
      100% { transform: translateY(-110vh) rotate(360deg) scale(1.8); opacity: 0; }
    }

    .petal {
      position: fixed;
      top: -10px;
      font-size: 22px;
      animation: fallDown 8s linear infinite;
      opacity: 0.9;
    }

    @keyframes fallDown {
      0% { transform: translateY(0) rotate(0deg); }
      100% { transform: translateY(110vh) rotate(360deg); }
    }
      100% { transform: translateY(-110vh) scale(1.8); opacity: 0; }
    }
  </style>
</head>
<body onload="startFireworks()">
  <div class="container" id="lock">
    <h2>Enter Password 💌</h2>
    <input type="password" id="pwd" placeholder="Only for Apshara" style="padding:10px;border-radius:10px;border:none" />
    <br><br>
    <button onclick="unlock()">Unlock ❤️</button>
  </div>

  <div class="container hidden" id="main">
    <h1>I LOVE YOU INFINITY APSHARA 💙♾️💗</h1>

    <button onclick="showLove()">Press Me</button>
    <br><br>
    <button onclick="showProposal()">💖 One More Surprise</button>
    <br><br>
    <button onclick="toggleMusic()">Play Music 🎵</button>

    <audio id="bgMusic" loop>
      <source src="love-music.mp3" type="audio/mpeg">
    </audio>

    <div id="surprise" class="hidden">
      <img src="your-image.jpg" alt="Apshara" />
      <div class="love-text" id="typing"></div>
      <p id="personalMsg" style="margin-top:15px;font-size:1.1rem;color:#ffd6e8;"></p>
      <div></div>
    </div>
  </div>

  <div id="proposal" class="hidden" style="position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.8);display:flex;align-items:center;justify-content:center;z-index:999;">
    <div style="background:white;color:#d63384;padding:30px;border-radius:25px;text-align:center;max-width:90%;">
      <h2>💍 Happy 3rd Month Anniversary, APSHARA 💖 💍</h2>
      <p style="font-size:1.2rem;">3 beautiful months together & many more to come ♾️💗</p>
      <button onclick="acceptProposal()" style="margin:10px;padding:10px 20px;border:none;border-radius:20px;background:#ff5fa2;color:white;">Happy Anniversary 💗</button>
      <button onclick="closeProposal()" style="margin:10px;padding:10px 20px;border:none;border-radius:20px;background:#ccc;">Awww 🙈</button>
    </div>
  </div>

  <script>
    function showLove() {
      document.getElementById('surprise').style.display = 'block';
      createHearts();
    }

    function toggleMusic() {
      const music = document.getElementById('bgMusic');
      if (music.paused) {
        music.play();
      } else {
        music.pause();
      }
    }

    function createHearts() {
      setInterval(() => {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.innerHTML = '💗';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 6000);
      }, 500);

      setInterval(() => {
        const petal = document.createElement('div');
        petal.className = 'petal';
        petal.innerHTML = '🌸';
        petal.style.left = Math.random() * 100 + 'vw';
        petal.style.animationDuration = (Math.random() * 4 + 6) + 's';
        document.body.appendChild(petal);
        setTimeout(() => petal.remove(), 8000);
      }, 600);

      typeText();
    }

    function typeText() {
      const text = 'I Love youuuuu moreeeee APSHARA 💗';
      let index = 0;
      const target = document.getElementById('typing');
      const interval = setInterval(() => {
        target.innerHTML += text[index];
        index++;
        if (index === text.length) {
          clearInterval(interval);
          showPersonalMessage();
        }
      }, 80);
    }

    function showPersonalMessage() {
      const msg = "These 3 months with you have been the happiest days of my life. Thank you for choosing me, for loving me, and for being you. Here’s to us and many more months together ♾️💗";
      document.getElementById('personalMsg').innerText = msg;
    }, 80);
    }, 400);
    }
  function unlock() {
      if (document.getElementById('pwd').value === 'apshara') {
        document.getElementById('lock').style.display = 'none';
        document.getElementById('main').style.display = 'block';
      } else {
        alert('Wrong password 💔');
      }
    }

    function startFireworks() {
      setInterval(() => {
        const fw = document.createElement('div');
        fw.innerHTML = '🎆';
        fw.style.position = 'fixed';
        fw.style.left = Math.random() * 100 + 'vw';
        fw.style.top = Math.random() * 50 + 'vh';
        fw.style.fontSize = '30px';
        document.body.appendChild(fw);
        setTimeout(() => fw.remove(), 2000);
      }, 800);
    }

    function showProposal() {
      document.getElementById('proposal').style.display = 'flex';
    }

    function closeProposal() {
      document.getElementById('proposal').style.display = 'none';
    }

    function acceptProposal() {
      document.getElementById('proposal').style.display = 'none';
      localStorage.setItem('proposalDate', new Date().toDateString());
      const celebration = document.createElement('div');
      celebration.style.position = 'fixed';
      celebration.style.top = '0';
      celebration.style.left = '0';
      celebration.style.width = '100%';
      celebration.style.height = '100%';
      celebration.style.background = 'linear-gradient(135deg,#ff9a9e,#fad0c4)';
      celebration.style.display = 'flex';
      celebration.style.flexDirection = 'column';
      celebration.style.alignItems = 'center';
      celebration.style.justifyContent = 'center';
      celebration.style.zIndex = '1000';
      celebration.innerHTML = `
        <h1 style="font-size:2.2rem;color:white;">💖 HAPPY 3 MONTHS TOGETHER 💖</h1>
        <h2 style="color:white;">APSHARA & ME 💖</h2>
        <p style="color:white;font-size:1.2rem;">${new Date().toDateString()}</p>
        <div style="font-size:3rem;">💖💖💖</div>
      `;
      document.body.appendChild(celebration);
    }, 800);
    }
  </script>
</body>
</html>
