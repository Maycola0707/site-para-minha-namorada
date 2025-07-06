<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Para o Amor da Minha Vida 💖</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to bottom, #ffd1dc, #ffe4ec);
      text-align: center;
      padding: 50px;
      color: #333;
      overflow: hidden;
      position: relative;
      transition: background-color 0.5s;
    }

    h1 {
      color: #d63384;
    }

    input, select, button {
      margin: 10px;
      padding: 10px;
      border-radius: 8px;
      border: none;
      font-size: 16px;
    }

    button {
      background-color: #d63384;
      color: white;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background-color: #c2185b;
    }

    #mensagemFinal {
      margin-top: 20px;
      font-size: 22px;
      color: #880e4f;
      font-weight: bold;
      animation: fadeIn 2s ease-in;
    }

    #duvida {
      display: none;
      margin-top: 30px;
    }

    #duvida img {
      max-width: 250px;
      border-radius: 12px;
      margin-bottom: 15px;
    }

    #duvidaTexto {
      font-size: 24px;
      color: black;
      background-color: #fff;
      padding: 12px;
      display: inline-block;
      border-radius: 10px;
      margin-bottom: 15px;
      font-weight: bold;
    }

    #botaoDesculpa {
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      background-color: black;
      color: white;
      border-radius: 8px;
      cursor: pointer;
    }

    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    .heart, .balloon, .carinho {
      position: absolute;
      animation: floatUp 6s linear infinite;
      z-index: 0;
    }

    .heart {
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
    }

    .heart::before, .heart::after {
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

    .balloon {
      width: 30px;
      height: 40px;
      border-radius: 50% 50% 45% 45%;
      background-color: pink;
      border: 2px solid #ff4081;
    }

    .carinho {
      font-size: 18px;
      color: #6a1b9a;
      font-weight: bold;
      opacity: 0.8;
    }

    @keyframes floatUp {
      0% {
        bottom: -40px;
        opacity: 0.9;
      }
      100% {
        bottom: 100%;
        opacity: 0;
        transform: translateY(-100px) rotate(360deg);
      }
    }
  </style>
</head>
<body onload="mensagensFlutuantes()">

  <h1>Oi, meu amor 💘</h1>
  <p>Digite seu nome e diga o quanto você me ama:</p>

  <input type="text" id="nome" placeholder="Seu nome"><br>

  <label for="amor">Quanto você me ama (0 a 10)?</label><br>
  <select id="amor">
    <option value="" disabled selected>Escolha</option>
    <option value="0">0</option>
    <option value="1">1</option>
    <option value="2">2</option>
    <option value="3">3</option>
    <option value="4">4</option>
    <option value="5">5</option>
    <option value="6">6</option>
    <option value="7">7</option>
    <option value="8">8</option>
    <option value="9">9</option>
    <option value="10">10</option>
  </select><br>

  <button onclick="confirmarAmor()">Confirmar</button>

  <div id="mensagemFinal"></div>

  <div id="duvida">
    <img src="12962815-8bcd-473c-8da3-918354ed4341.png" alt="Imagem triste">
    <div id="duvidaTexto">TEM CERTEZA AMORZINHO?</div><br>
    <button id="botaoDesculpa" onclick="location.reload()">ME DESCULPA MEU AMOR</button>
  </div>

  <script>
    const mensagensCarinho = [
      "Te amo 💖",
      "Minha princesa 👑",
      "Você é única ✨",
      "Amor da minha vida 💘",
      "Linda demais 😍",
      "Meu tudo 💞",
      "Sempre com você 💍",
      "Você me completa ❤️"
    ];

    function mensagensFlutuantes() {
      setInterval(() => {
        const carinho = document.createElement("div");
        carinho.classList.add("carinho");
        carinho.innerText = mensagensCarinho[Math.floor(Math.random() * mensagensCarinho.length)];
        carinho.style.left = Math.random() * 100 + "vw";
        carinho.style.animationDuration = 4 + Math.random() * 4 + "s";
        document.body.appendChild(carinho);
        setTimeout(() => carinho.remove(), 7000);
      }, 1000);
    }

    function confirmarAmor() {
      const nome = document.getElementById("nome").value;
      const amor = document.getElementById("amor").value;
      const mensagem = document.getElementById("mensagemFinal");
      const duvida = document.getElementById("duvida");

      if (!nome || amor === "") {
        mensagem.innerHTML = "Preencha tudo direitinho, amor 💌";
        return;
      }

      if (amor !== "10") {
        document.body.style.backgroundColor = "#ff4c4c";
        mensagem.innerHTML = "";
        duvida.style.display = "block";
        return;
      }

      document.body.style.background = "linear-gradient(to bottom, #ffd1dc, #ffe4ec)";
      duvida.style.display = "none";
      mensagem.innerHTML = `${nome}, agora você é minha pra sempre 💍💖<br>(e me ama ${amor}/10 😍)`;

      window.open("https://www.youtube.com/watch?v=450p7goxZqg", "_blank");

      for (let i = 0; i < 20; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = 4 + Math.random() * 4 + "s";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 7000);
      }

      for (let i = 0; i < 10; i++) {
        const balloon = document.createElement("div");
        balloon.classList.add("balloon");
        balloon.style.left = Math.random() * 100 + "vw";
        balloon.style.backgroundColor = getRandomColor();
        balloon.style.animationDuration = 5 + Math.random() * 5 + "s";
        document.body.appendChild(balloon);
        setTimeout(() => balloon.remove(), 10000);
      }
    }

    function getRandomColor() {
      const cores = ["#ff4081", "#f48fb1", "#ce93d8", "#81d4fa", "#ffcc80"];
      return cores[Math.floor(Math.random() * cores.length)];
    }
  </script>

</body>
</html>
