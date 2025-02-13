<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine?</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #ffebee;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .container {
      text-align: center;
      background-color: #fff;
      padding: 40px;
      border-radius: 15px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
    }
    h1 {
      color: #e91e63;
      font-size: 2.5em;
      margin-bottom: 20px;
    }
    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
    }
    button {
      padding: 10px 20px;
      font-size: 1.2em;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.2s ease;
    }
    button.yes {
      background-color: #e91e63;
      color: white;
    }
    button.no {
      background-color: #ccc;
      color: black;
    }
    button:hover {
      transform: scale(1.1);
    }
    .hearts {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      pointer-events: none;
    }
    .hearts span {
      position: absolute;
      color: #e91e63;
      font-size: 20px;
      animation: float 5s linear infinite;
    }
    @keyframes float {
      0% { transform: translateY(-10%); opacity: 1; }
      100% { transform: translateY(110%); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Will You Be My Valentine? 💖</h1>
    <div class="buttons">
      <button class="yes" onclick="alert('Yay! You made me the happiest! 💕')">Yes</button>
      <button class="no" onmouseover="moveButton(this)">No</button>
    </div>
  </div>

  <div class="hearts">
    <!-- Hearts floating in the background -->
    <span>💖</span>
    <span>💕</span>
    <span>💘</span>
    <span>💓</span>
    <span>💝</span>
  </div>

  <script>
    function moveButton(button) {
      const x = Math.random() * (window.innerWidth - button.offsetWidth);
      const y = Math.random() * (window.innerHeight - button.offsetHeight);
      button.style.position = 'absolute';
      button.style.left = `${x}px`;
      button.style.top = `${y}px`;
    }

    // Add floating hearts dynamically
    const heartsContainer = document.querySelector('.hearts');
    for (let i = 0; i < 20; i++) {
      const heart = document.createElement('span');
      heart.innerHTML = '💖';
      heart.style.left = `${Math.random() * 100}%`;
      heart.style.animationDuration = `${Math.random() * 3 + 2}s`;
      heartsContainer.appendChild(heart);
    }
  </script>
</body>
</html>
