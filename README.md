
<html lang="bn">
<head>
  <meta charset="UTF-8" />
  <title>Simple Fun Website</title>
  <style>
    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      background: #f2f2f2;
    }
    .box {
      text-align: center;
    }
    button {
      padding: 15px 25px;
      margin: 10px;
      font-size: 18px;
      cursor: pointer;
      border-radius: 8px;
      border: none;
    }
    #good {
      background: #4caf50;
      color: white;
      position: absolute;
    }
    #bad {
      background: #f44336;
      color: white;
    }
    #sadText {
      font-size: 40px;
      margin-top: 20px;
      display: none;
    }
  </style>
</head>
<body>
  <div class="box">
    <button id="good">Sob kisu valo</button>
    <br />
    <button id="bad">Sob kisu kharap</button>
    <div id="sadText">SO SAD 😫😫</div>
  </div>

  <script>
    const goodBtn = document.getElementById("good");
    const badBtn = document.getElementById("bad");
    const sadText = document.getElementById("sadText");

    goodBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 150);
      const y = Math.random() * (window.innerHeight - 60);
      goodBtn.style.left = x + "px";
      goodBtn.style.top = y + "px";
    });

    badBtn.addEventListener("click", () => {
      sadText.style.display = "block";
    });
  </script>
</body>
</html>
