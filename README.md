<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Cinta Untuk Netanya</title>
  <style>
    body {
      margin: 0;
      background: linear-gradient(to bottom, #fff0f5, #ffe6e6);
      height: 100vh;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: 'Arial', sans-serif;
    }

    button {
      padding: 15px 30px;
      font-size: 1.2em;
      background-color: #ff4d88;
      border: none;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #e60073;
    }

    #message {
      margin-top: 30px;
      font-size: 2em;
      color: #cc0066;
      font-weight: bold;
      display: none;
      animation: fadeInUp 1s ease-out;
    }

    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: fall linear infinite;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: -10px;
      top: 0;
    }

    @keyframes fall {
      0% {
        top: -10%;
        opacity: 1;
        transform: translateX(0) rotate(45deg);
      }
      100% {
        top: 110%;
        opacity: 0;
        transform: translateX(30px) rotate(45deg);
      }
    }
  </style>
</head>
<body>

  <button onclick="showLove()">Klik Aku</button>
  <div id="message">Netanya Salurapa Tallulembang</div>

  <script>
    function showLove() {
      const message = document.getElementById('message');
      message.style.display = 'block';

      setInterval(() => {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (2 + Math.random() * 3) + 's';
        document.body.appendChild(heart);
        setTimeout(() => {
          heart.remove();
        }, 5000);
      }, 200);
    }
  </script>

</body>
</html>
