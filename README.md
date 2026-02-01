
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JANHVI 💖 My Valentine</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Comic Sans MS', cursive;
      overflow: hidden;
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      color: pink;
      font-size: 20px;
      animation: floatUp 6s linear infinite;
      opacity: 0.7;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }

    .card {
      background: #fff0f6;
      padding: 30px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 15px 35px rgba(0,0,0,0.25);
      width: 330px;
      z-index: 2;
    }

    h1 {
      color: #ff4d6d;
      font-size: 26px;
    }

    p {
      color: #ff758f;
      font-size: 18px;
    }

    .buttons {
      margin-top: 20px;
      position: relative;
      height: 120px;
    }

    button {
      padding: 12px 26px;
      border: none;
      border-radius: 30px;
      font-size: 16px;
      cursor: pointer;
      position: absolute;
      transition: 0.3s;
    }

    #yesBtn {
      background: #ff4d6d;
      color: white;
      left: 50%;
      transform: translateX(-50%);
      bottom: 10px;
    }

    #noBtn {
      background: #ffd6e0;
      color: #ff4d6d;
      right: 20px;
      bottom: 10px;
    }

    .yay {
      display: none;
      flex-direction: column;
      align-items: center;
    }

    .yay h1 {
      font-size: 30px;
      animation: pop 0.5s infinite alternate;
    }

    @keyframes pop {
      from { transform: scale(1); }
      to { transform: scale(1.15); }
    }

    img {
      width: 230px;
      margin-top: 15px;
    }
  </style>
</head>
<body>

<!-- Background music -->
<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div class="card" id="questionCard">
  <h1>Hey JANHVI 💖</h1>
  <p>Will you be my Valentine? 🌹</p>

  <div class="buttons">
    <button id="yesBtn">Yes 💕</button>
    <button id="noBtn">No 😝</button>
  </div>
</div>

<div class="card yay" id="yayCard">
  <h1>YAYAYAYAYAY 💕🐼</h1>
  <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" alt="Panda with roses">
</div>

<script>
  const noBtn = document.getElementById("noBtn");
  const yesBtn = document.getElementById("yesBtn");
  const questionCard = document.getElementById("questionCard");
  const yayCard = document.getElementById("yayCard");

  noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * 250 - 125;
    const y = Math.random() * 150 - 75;
    noBtn.style.transform = `translate(${x}px, ${y}px)`;
  });

  yesBtn.addEventListener("click", () => {
    questionCard.style.display = "none";
    yayCard.style.display = "flex";
  });

  // Create floating hearts
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💗";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 15 + "px";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 6000);
  }, 400);
</script>

</body>
</html>
