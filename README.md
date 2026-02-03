<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine 💖</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Poppins', sans-serif;
      overflow: hidden;
    }

    .container {
      text-align: center;
      background: rgba(255, 255, 255, 0.2);
      backdrop-filter: blur(10px);
      padding: 40px 30px;
      border-radius: 25px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);
      max-width: 350px;
      width: 90%;
    }

    h1 {
      font-family: 'Pacifico', cursive;
      color: #fff;
      font-size: 2.2rem;
      margin-bottom: 30px;
      text-shadow: 2px 2px 10px rgba(0,0,0,0.2);
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      position: relative;
    }

    button {
      border: none;
      padding: 12px 28px;
      font-size: 1.1rem;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s ease;
      font-weight: 600;
    }

    #yesBtn {
      background: #ff4d6d;
      color: white;
      box-shadow: 0 10px 20px rgba(255, 77, 109, 0.4);
    }

    #yesBtn:hover {
      transform: scale(1.1);
    }

    #noBtn {
      background: white;
      color: #ff4d6d;
      position: relative;
    }

    .message {
      margin-top: 30px;
      font-size: 1.3rem;
      color: white;
      display: none;
      animation: fadeIn 1s ease forwards;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(10px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      color: rgba(255, 255, 255, 0.6);
      font-size: 20px;
      animation: floatUp 6s linear infinite;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) scale(0.5);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.2);
        opacity: 0;
      }
    }

    footer {
      margin-top: 20px;
      font-size: 0.8rem;
      color: #fff;
      opacity: 0.8;
    }
  </style>
</head>

<body>

  <div class="container">
    <h1>Will you be my Valentine today? 💖</h1>

    <div class="buttons">
      <button id="yesBtn">Yes 💘</button>
      <button id="noBtn">No 💔</button>
    </div>

    <div class="message" id="message">
      You just made my day ❤️<br>Happy Valentine’s Day!
    </div>

    <footer>Made with ❤️ just for you</footer>
  </div>

  <script>
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const message = document.getElementById("message");

    yesBtn.addEventListener("click", () => {
      message.style.display = "block";
      yesBtn.style.display = "none";
      noBtn.style.display = "none";
      createHearts();
    });

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    });

    function createHearts() {
      for (let i = 0; i < 20; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 6000);
      }
    }
  </script>

</body>
</html>
