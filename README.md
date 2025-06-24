<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Do You Love Me?</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #fff0f6;
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
    }

    .container {
      margin: 20px auto;
      padding: 10px;
      max-width: 600px;
      width: 90%;
    }

    img {
      width: 100%;
      max-width: 300px;
      border-radius: 12px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }

    h2 {
      margin: 20px 0;
      font-size: 26px;
      color: #d63384;
    }

    h3 {
      margin: 20px 0;
      font-size: 22px;
      color: #000;
    }

    .button-container {
      position: relative;
      height: 80px;
    }

    .btn {
      padding: 10px 25px;
      margin: 10px 5px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
      position: relative;
    }

    .yes-btn {
      background-color: #ff69b4;
      color: white;
    }

    .no-btn {
      background-color: #f8d7da;
      color: #721c24;
      position: absolute;
    }

    .btn:hover {
      transform: scale(1.1);
    }

    .result-container,
    .rejection-container {
      display: none;
      margin-top: 20px;
    }

    .heart-emoji {
      font-size: 60px;
      display: inline-block;
      margin-top: 20px;
      animation: beat-glow 1.5s infinite;
      filter: drop-shadow(0 0 10px #ff4d88);
    }

    @keyframes beat-glow {
      0% {
        transform: scale(1) rotate(0deg);
        filter: drop-shadow(0 0 5px #ff4d88);
      }
      25% {
        transform: scale(1.2) rotate(-10deg);
        filter: drop-shadow(0 0 15px #ff4d88);
      }
      50% {
        transform: scale(1) rotate(10deg);
        filter: drop-shadow(0 0 5px #ff4d88);
      }
      75% {
        transform: scale(1.3) rotate(-5deg);
        filter: drop-shadow(0 0 20px #ff4d88);
      }
      100% {
        transform: scale(1) rotate(0deg);
        filter: drop-shadow(0 0 5px #ff4d88);
      }
    }

    /* Mobile responsive tweaks */
    @media (max-width: 480px) {
      h2 {
        font-size: 22px;
      }

      h3 {
        font-size: 18px;
      }

      .btn {
        font-size: 16px;
        padding: 8px 20px;
      }

      .heart-emoji {
        font-size: 50px;
      }
    }
  </style>
</head>
<body>

  <div class="question-container container">
    <img src="loveyou.webp" alt="Love Gif">
    <h2 class="question">Do you love sri?</h2>
    <div class="button-container">
      <button class="yes-btn btn js-yes-btn">Yes</button>
      <button class="no-btn btn js-no-btn" id="noButton">No</button>
    </div>
  </div>

  <!-- YES response -->
  <div class="result-container container" id="resultBox">
    <img src="propose.gif" alt="GIF Image">
    <h2>I knew it....My princess..!!</h2>
    <h3>I am always yours</h3>
    <div class="heart-emoji">❤️</div>
  </div>

 <script>
  const yesBtn = document.querySelector('.js-yes-btn');
  const noBtn = document.getElementById('noButton');
  const resultBox = document.getElementById('resultBox');
  const rejectionBox = document.getElementById('rejectionBox');

  yesBtn.addEventListener('click', () => {
    resultBox.style.display = 'block';
    rejectionBox.style.display = 'none';
  });

  function moveButtonAway() {
    const buttonContainer = document.querySelector('.button-container');
    const maxX = buttonContainer.offsetWidth - noBtn.offsetWidth;
    const maxY = buttonContainer.offsetHeight - noBtn.offsetHeight;

    const randomX = Math.floor(Math.random() * maxX);
    const randomY = Math.floor(Math.random() * maxY);

    noBtn.style.left = `${randomX}px`;
    noBtn.style.top = `${randomY}px`;
  }

  // Escape on mouse hover (desktop)
  noBtn.addEventListener('mouseover', moveButtonAway);

  // On touch (mobile), show rejection message instead of moving
  noBtn.addEventListener('touchstart', (e) => {
    e.preventDefault(); // Prevent accidental click
    resultBox.style.display = 'none';
    rejectionBox.style.display = 'block';
  });
</script>

</body>
</html>


