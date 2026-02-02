**index.html**  
<!DOCTYPE html>  
<html lang="en">  
<head>  
  <meta charset="UTF-8">  
  <title>Esha's Valentine</title>  
  <style>  
    body {  
      background-color: pink;  
      text-align: center;  
      font-family: Arial, sans-serif;  
      margin-top: 80px;  
      overflow: hidden;  
    }  
  
    h1 {  
      font-size: 50px;  
      color: #d1005d;  
    }  
  
    p {  
      font-size: 24px;  
      color: #a10045;  
    }  
  
    .buttons {  
      margin-top: 40px;  
    }  
  
    button {  
      font-size: 35px;  
      padding: 20px 50px;  
      background-color: hotpink;  
      color: white;  
      border: none;  
      border-radius: 15px;  
      margin: 10px;  
      cursor: pointer;  
    }  
  
    #noBtn {  
      position: absolute;  
    }  
  
    #meme {  
      display: none;  
      margin-top: 40px;  
    }  
  
    img {  
      width: 300px;  
      border-radius: 20px;  
    }  
  
    /* Floating hearts */  
    .heart {  
      position: fixed;  
      bottom: -20px;  
      font-size: 24px;  
      animation: floatUp 6s linear infinite;  
    }  
  
    @keyframes floatUp {  
      from { transform: translateY(0); opacity: 1; }  
      to { transform: translateY(-100vh); opacity: 0; }  
    }  
  </style>  
</head>  
  
<body>  
  
  <h1>💖 Esha, Will You Be My Valentine? 💖</h1>  
  <p>From Tom 💌</p>  
  
  <div class="buttons">  
    <button onclick="yesClicked()">YES 💕</button>  
    <button id="noBtn" ontouchstart="moveNo()" onmouseover="moveNo()">NO 🙈</button>  
  </div>  
  
  <div id="meme">  
    <h2>You just made my day, Esha 😍</h2>  
    <img src="https://media.giphy.com/media/l4FGpPki5v2Bcd6Ss/giphy.gif">  
  </div>  
  
  <audio id="song">  
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3" type="audio/mpeg">  
  </audio>  
  
  <script>  
    // Floating hearts  
    setInterval(() => {  
      const heart = document.createElement("div");  
      heart.className = "heart";  
      heart.innerHTML = "💖";  
      heart.style.left = Math.random() * 100 + "vw";  
      heart.style.animationDuration = 3 + Math.random() * 3 + "s";  
      document.body.appendChild(heart);  
      setTimeout(() => heart.remove(), 6000);  
    }, 300);  
  
    // NO button runs away  
    function moveNo() {  
      let x = Math.random() * (window.innerWidth - 100);  
      let y = Math.random() * (window.innerHeight - 50);  
      const noBtn = document.getElementById("noBtn");  
      noBtn.style.left = x + "px";  
      noBtn.style.top = y + "px";  
    }  
  
    // YES clicked  
    function yesClicked() {  
      document.getElementById("meme").style.display = "block";  
      document.getElementById("song").play();  
      launchConfetti();  
    }  
  
    // Confetti  
    function launchConfetti() {  
      for (let i = 0; i < 100; i++) {  
        const confetti = document.createElement("div");  
        confetti.innerHTML = "🎉";  
        confetti.style.position = "fixed";  
        confetti.style.left = Math.random() * 100 + "vw";  
        confetti.style.top = "-20px";  
        confetti.style.fontSize = "20px";  
        confetti.style.animation = "fall 3s linear";  
        document.body.appendChild(confetti);  
        setTimeout(() => confetti.remove(), 3000);  
      }  
    }  
  
    const style = document.createElement("style");  
    style.innerHTML = `  
      @keyframes fall {  
        to {  
          transform: translateY(100vh);  
          opacity: 0;  
        }  
      }  
    `;  
    document.head.appendChild(style);  
  </script>  
  
</body>  
</html>  
