<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Kişisel Sayfa - Emre Çil</title>
  <link rel="icon" type="image/x-icon" href="favicon.ico">
  <style>
      .glow-btn {
    position: relative;
    z-index: 0;
    overflow: hidden;
    transition: 0.4s ease-in-out;
    box-shadow: 0 0 5px #00e6e6, 0 0 10px #00e6e6;
    cursor: pointer;
  }

  .glow-btn::before {
    content: "";
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(45deg, #00e6e6, #1fc8db, #2cb5e8, #1fc8db);
    animation: rotate 4s linear infinite;
    z-index: -1;
    filter: blur(8px);
  }

  @keyframes rotate {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }

  body {
    background-color: #1e1e2f;
    color: #e0e0e0;
    font-family: Arial, sans-serif;
    margin: 0;
  }

  a { color: #7cc6fe; }

  .btn {
    background-color: #7cc6fe;
    color: #1e1e2f;
    padding: 6px 12px;
    font-size: 14px;
    border-radius: 6px;
    text-decoration: none;
    font-weight: 600;
    display: inline-block;
    min-width: 120px;
    text-align: center;
    margin: 4px;
    cursor: pointer;
    border: none;
  }

  .btn:hover { background-color: #5fb2ec; }

  .link-container {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-top: 30px;
  }

  .profil-foto {
    position: absolute;
    left: 450px;
    top: 100px;
    width: 120px;
    border-radius: 50%;
    box-shadow: 0 0 10px rgba(0,0,0,0.2);
  }

  .icerik-kapsayici {
    display: flex;
    flex-direction: row;
    gap: 20px;
    padding: 20px;
  }

  .icerik-sol { flex: 3; }

  .oyunlar-sag {
    flex: 1;
    background-color: #2a2a40;
    padding: 20px;
    border-radius: 8px;
    height: fit-content;
  }

  .oyunlar-sag h3 { color: #7cc6fe; margin-top: 0; }
  .oyunlar-sag ul { list-style: none; padding: 0; margin: 0; }
  .oyunlar-sag li { margin-bottom: 10px; }
  .oyunlar-sag a { color: #e0e0e0; text-decoration: none; cursor: pointer; }
  .oyunlar-sag a:hover { text-decoration: underline; }

  /* ORTAK OYUN ALANI STİLİ */
  .oyun-alani {
    margin-top: 60px;
    display: none; /* Varsayılan olarak gizli */
    padding: 20px;
    border: 3px solid cyan;
    box-shadow: 0px 0px 15px cyan, 0px 0px 15px cyan inset;
    border-radius: 12px;
    background-color: #292940;
    text-align: center;
  }

  /* ADAM ASMACA STİLLERİ */
  .hangman-word { letter-spacing: 10px; font-size: 24px; margin-bottom: 20px; }
  .letter-btn {
    padding: 8px 12px; margin: 4px; font-size: 16px; border-radius: 5px;
    background-color: #444; color: #fff; border: none; cursor: pointer;
  }
  .letter-btn.wrong { background-color: #c0392b; }
  .kategori-secim { display: flex; justify-content: center; gap: 20px; margin: 20px 0 30px 0; }
  .ipucu {
    background-color: #44476a; color: #fff; padding: 8px 16px;
    border-radius: 6px; font-size: 16px; margin-bottom: 18px; display: inline-block;
  }

  /* XOX STİLLERİ */
  .turn-container {
      width: 170px; height: 50px; margin: auto; display: grid;
      grid-template-columns: 1fr 1fr; grid-template-rows: 1fr 1fr; position: relative;
  }
  .turn-container h3 { margin: 0; grid-column-start: 1; grid-column-end: 3; font-size: 1rem; color: #fff; text-align: center; }
  .turn-box { border: 3px solid #000; font-size: 1.2rem; font-weight: 700; display: flex; align-items: center; justify-content: center; z-index: 1; color: white;}
  .turn-container .bg {
      position: absolute; bottom: 0; left: 0; width: 85px; height: 25px;
      background-color: #FF2E63; z-index: 0; transition: left 0.2s ease-in-out;
  }
  .main-grid {
      display: grid; grid-template-columns: repeat(3, 1fr); grid-template-rows: repeat(3, 1fr);
      height: 250px; width: 250px; margin: 30px auto; border: 2px solid #000;
  }
  .box {
      border: 2px solid #000; font-size: 2.5rem; font-weight: 700;
      display: flex; align-items: center; justify-content: center; cursor: pointer; color: white;
  }
  .box:hover { background-color: #FF2E63; }

  /* YILAN OYUNU STİLLERİ */
  #gameCanvas {
      background-color: #f0f0f0;
      border: 2px solid #333;
      display: block;
      margin: 0 auto;
  }
  .mobile-controls button {
      background-color: #444;
      color: white;
      border: 1px solid #7cc6fe;
      border-radius: 5px;
      margin: 2px;
      width: 50px;
      height: 40px;
      font-size: 20px;
      cursor: pointer;
  }
  .mobile-controls button:active { background-color: #5fb2ec; }


  /* RESPONSIVE */
  @media (max-width: 768px) {
    .icerik-kapsayici { flex-direction: column; padding: 10px; gap: 10px; }
    .profil-foto { position: static; display: block; margin: 20px auto; width: 80px; }
    .btn { min-width: 100px; font-size: 13px; padding: 5px 10px; }
    .oyun-alani { padding: 10px; }
    .hangman-word { letter-spacing: 6px; font-size: 18px; }
    #svg-hangman-container svg { width: 150px; height: auto; }
    .letter-btn { padding: 6px 10px; font-size: 14px; }
    .oyunlar-sag { margin-top: 30px; }
    h1 { font-size: 22px; }
  }

  h1 { font-size: 28px; margin-bottom: 10px; }
</style>
</head>
<body>
<img src="profil.jpeg" alt="Profil Fotoğrafı" class="profil-foto">

<div class="icerik-kapsayici">
  <div class="icerik-sol">
    <h1>Merhaba, ben Emre 👋</h1>
    <p>Bu benim kişisel sayfam, zamanla gelişecek.</p>

    <h2>📸 Hakkımda</h2>
    <p>Ben Emre Çil. Gazi Üniversitesi'nde Enerji Sistemleri Mühendisliği öğrencisiyim.</p>

    <h2>🔗 Bağlantılar</h2>
    <div class="link-container">
      <a href="https://github.com/cilemre" target="_blank" class="btn">GitHub</a>
      <a href="https://www.linkedin.com/in/emre-%C3%A7il-95878731b/" target="_blank" class="btn">LinkedIn</a>
      <a href="https://www.instagram.com/emrecl__/" target="_blank" class="btn">Instagram</a>
    </div>

    <div class="oyun-alani" id="oyun-alani">
      <h2 id="oyun-baslik">Adam Asmaca</h2>
      <div id="kategoriBaslik" style="text-align: center; font-size: 17px; margin-bottom: 8px;">Kategori Seçiniz:</div>
      <div id="kategoriSecim" class="kategori-secim">
        <button class="btn glow-btn" onclick="kategoriSec('muhendislik')">Mühendislik</button>
        <button class="btn glow-btn" onclick="kategoriSec('film')">Film</button>
      </div>
      <div id="ipucuAlani" class="ipucu" style="display: none;"></div>
      <p id="hakSatiri" style="display: none;"><strong>Kalan Hak:</strong> <span id="hakSayisi"></span></p>
      <div id="wordDisplay" class="hangman-word" style="display: none;"></div>
      <div id="letters" style="display: none;"></div>
      <p id="status" style="display: none;"></p>
      <div id="svg-hangman-container" style="text-align: center; margin-top: 20px; display: none;">
        <svg id="hangman-svg" viewBox="0 0 200 250" style="width: 100%; max-width: 200px; height: auto;">
          <line x1="20" y1="230" x2="180" y2="230" stroke="#888" stroke-width="4"/>
          <line x1="50" y1="230" x2="50" y2="20" stroke="#888" stroke-width="4"/>
          <line x1="50" y1="20" x2="130" y2="20" stroke="#888" stroke-width="4"/>
          <line x1="130" y1="20" x2="130" y2="50" stroke="#888" stroke-width="4"/>
          <circle id="svg-head" cx="130" cy="70" r="20" stroke="#fff" stroke-width="3" fill="none" style="display: none;"/>
          <line id="svg-body" x1="130" y1="90" x2="130" y2="150" stroke="#fff" stroke-width="3" style="display: none;"/>
          <line id="svg-arm-left" x1="130" y1="110" x2="100" y2="130" stroke="#fff" stroke-width="3" style="display: none;"/>
          <line id="svg-arm-right" x1="130" y1="110" x2="160" y2="130" stroke="#fff" stroke-width="3" style="display: none;"/>
          <line id="svg-leg-left" x1="130" y1="150" x2="110" y2="190" stroke="#fff" stroke-width="3" style="display: none;"/>
          <line id="svg-leg-right" x1="130" y1="150" x2="150" y2="190" stroke="#fff" stroke-width="3" style="display: none;"/>
        </svg>
      </div>
      <button id="yenidenBaslatBtn" onclick="oyunuYenidenBaslat()" class="btn glow-btn" style="margin-top: 20px; display: none;">Yeniden Başlat</button>
    </div>

    <div class="oyun-alani" id="xox-alani" style="display:none;">
      <h2>Tic Tac Toe (XOX)</h2>
      <div class="turn-container">
        <h3>Sıra</h3>
        <div class="turn-box align">X</div>
        <div class="turn-box align">O</div>
        <div class="bg"></div>
      </div>
      <div class="main-grid">
        <div class="box align"></div>
        <div class="box align"></div>
        <div class="box align"></div>
        <div class="box align"></div>
        <div class="box align"></div>
        <div class="box align"></div>
        <div class="box align"></div>
        <div class="box align"></div>
        <div class="box align"></div>
      </div>
      <h2 id="xox-results"></h2>
      <button id="xox-play-again" class="btn glow-btn" style="display:none;">Tekrar Oyna</button>
    </div>

    <div class="oyun-alani" id="snake-alani" style="display:none;">
        <h2>🐍 Yılan Oyunu</h2>
        <p>Skor: <span id="snakeScore">0</span></p>
        
        <canvas id="gameCanvas" width="300" height="300"></canvas>
        
        <div class="mobile-controls" style="margin-top: 15px;">
            <div><button onclick="changeSnakeDirection('UP')">⬆️</button></div>
            <div style="margin: 5px;">
                <button onclick="changeSnakeDirection('LEFT')">⬅️</button>
                <button onclick="changeSnakeDirection('RIGHT')">➡️</button>
            </div>
            <div><button onclick="changeSnakeDirection('DOWN')">⬇️</button></div>
        </div>
    
        <button onclick="startSnakeGame()" class="btn glow-btn" style="margin-top: 20px;">Yeniden Başlat</button>
    </div>

    <hr>
    <p style="text-align: center; margin-top: 40px; font-size: 14px; color: #999;">
      İletişim için: <strong>emre.cil@gazi.edu.tr</strong>
    </p>
  </div>

  <aside class="oyunlar-sag">
    <h3>🎮 Oyunlar</h3>
    <ul>
      <li><a onclick="oyunGoster()">Adam Asmaca</a></li>
      <li><a onclick="xoxGoster()">XOX</a></li>
      <li><a onclick="snakeGoster()">Yılan Oyunu</a></li>
    </ul>
  </aside>
</div>

<script>
  // --- ADAM ASMACA KODLARI ---
  const kelimeler = {
    muhendislik: [
      { kelime: "Termodinamik", ipucu: "Isı, enerji ve dengeyle ilgilenen mühendislik dalı" },
      { kelime: "Türbin", ipucu: "Dönme hareketiyle elektrik üreten makine" },
      { kelime: "GüneşEnerjisi", ipucu: "Yenilenebilir, fotovoltaik panellerle elde edilir" },
      { kelime: "Akışkanlar", ipucu: "Gaz ve sıvıların davranışlarını inceleyen mühendislik konusu" },
      { kelime: "Verim", ipucu: "Girdiye göre çıktının oranını belirten kavram" },
      { kelime: "Radyatör", ipucu: "Isı yaymak için kullanılan cihaz" },
      { kelime: "Jeotermal", ipucu: "Yerin altındaki ısıdan faydalanan enerji türü" },
      { kelime: "Entalpi", ipucu: "Termodinamikte toplam enerji ölçütü" },
      { kelime: "Direnç", ipucu: "Elektrik akımına karşı koyan devre elemanı" },
      { kelime: "Batarya", ipucu: "Elektrik enerjisini kimyasal olarak depolar" },
      { kelime: "KinetikEnerji", ipucu: "Hareket halindeki cisimlerin enerjisi" },
      { kelime: "IsıPompası", ipucu: "Isı transferi için kullanılan cihaz" },
      { kelime: "Frekans", ipucu: "Bir olayın birim zamanda tekrar sayısı" },
      { kelime: "Voltaj", ipucu: "Elektrik potansiyel farkı" },
      { kelime: "Otomasyon", ipucu: "İnsan müdahalesi olmadan sistemlerin çalışması" },
      { kelime: "Statik", ipucu: "Duran sistemlerdeki kuvvet dengesiyle ilgilenir" },
      { kelime: "Entropi", ipucu: "Düzensizliğin ölçüsü, termodinamiğin temel kavramı" }
    ],
    film: [
      { kelime: "Inception", ipucu: "Rüya içinde rüya konusunu işleyen bilim kurgu filmi" },
      { kelime: "Interstellar", ipucu: "Kara delik ve zaman yolculuğu temalı uzay filmi" },
      { kelime: "Titanic", ipucu: "Gerçek bir gemi kazasına dayanan romantik film" },
      { kelime: "Matrix", ipucu: "Gerçeklik ve simülasyon üzerine felsefi film" },
      { kelime: "Avatar", ipucu: "Mavi tenli yaratıkların yaşadığı gezegen" },
      { kelime: "Gladiator", ipucu: "Roma İmparatorluğu döneminde geçen bir intikam filmi" },
      { kelime: "Joker", ipucu: "Gotham'ın meşhur kötü karakteri" },
      { kelime: "Batman", ipucu: "Özel güçleri olmayan multimilyoner süper kahraman" },
      { kelime: "Godfather", ipucu: "Mafya dünyasında geçen efsanevi bir film serisi" },
      { kelime: "Parasite", ipucu: "Güney Kore yapımı, sınıf ayrımını anlatan film" },
      { kelime: "Dune", ipucu: "Çöl gezegeninde geçen bir bilim kurgu destanı" },
      { kelime: "FightClub", ipucu: "kulübü’nün ilk kuralı,kulüp hakkında konuşmamaktır." },
      { kelime: "ForrestGump", ipucu: "\"Koş Forrest koş!\" repliğiyle ünlü film" },
      { kelime: "Avengers", ipucu: "Süper kahramanların bir araya geldiği Marvel filmi" },
      { kelime: "Deadpool", ipucu: "Alaycı ve esprili bir süper kahraman" },
      { kelime: "Frozen", ipucu: "Buz büyüleri yapan prensesin hikayesi" },
      { kelime: "HarryPotter", ipucu: "Büyücülük okulunda okuyan çocuk" },
      { kelime: "StarWars", ipucu: "Işın kılıçları ve galaktik savaşlar" },
      { kelime: "Shrek", ipucu: "Bataklıkta yaşayan yakın arkadaşı eşşek olan kişi" }
    ]
  };

  let secilenKelime = "";
  let dogruHarfler = [];
  let hataliTahmin = 0;
  const maxHak = 6;

  function oyunGoster() {
    hideAllGames();
    document.getElementById("oyun-alani").style.display = "block";
    // Sıfırlama işlemleri vs.
  }

  function kategoriSec(kategori) {
    const havuz = kelimeler[kategori];
    const secim = havuz[Math.floor(Math.random() * havuz.length)];
    secilenKelime = secim.kelime.toUpperCase();
    const secilenIpucu = secim.ipucu;
    dogruHarfler = [];
    hataliTahmin = 0;
    
    document.getElementById("kategoriSecim").style.display = "none";
    document.getElementById("kategoriBaslik").style.display = "none";
    document.getElementById("ipucuAlani").innerText = "İpucu: " + secilenIpucu;
    document.getElementById("ipucuAlani").style.display = "inline-block";
    document.getElementById("hakSatiri").style.display = "block";
    document.getElementById("wordDisplay").style.display = "block";
    document.getElementById("letters").style.display = "block";
    document.getElementById("status").style.display = "block";
    document.getElementById("svg-hangman-container").style.display = "block";
    document.getElementById("yenidenBaslatBtn").style.display = "inline-block";
    document.getElementById("status").innerText = "";
    harfleriOlustur();
    guncelleEkran();
    sifirlaAdamCizimi();
  }

  function oyunuYenidenBaslat() {
    secilenKelime = "";
    dogruHarfler = [];
    hataliTahmin = 0;
    document.getElementById("kategoriSecim").style.display = "flex";
    document.getElementById("kategoriBaslik").style.display = "block";
    document.getElementById("ipucuAlani").style.display = "none";
    document.getElementById("hakSatiri").style.display = "none";
    document.getElementById("wordDisplay").style.display = "none";
    document.getElementById("letters").style.display = "none";
    document.getElementById("status").style.display = "none";
    document.getElementById("svg-hangman-container").style.display = "none";
    document.getElementById("yenidenBaslatBtn").style.display = "none";
    document.getElementById("hakSayisi").innerText = maxHak;
    document.getElementById("wordDisplay").innerText = "";
    document.getElementById("letters").innerHTML = "";
    sifirlaAdamCizimi();
  }

  function harfleriOlustur() {
    const lettersDiv = document.getElementById("letters");
    lettersDiv.innerHTML = "";
    for (let i = 65; i <= 90; i++) {
      const btn = document.createElement("button");
      btn.innerText = String.fromCharCode(i);
      btn.className = "letter-btn";
      btn.id = "btn-" + btn.innerText;
      btn.onclick = () => harfTahmin(btn.innerText, btn);
      lettersDiv.appendChild(btn);
    }
  }

  function harfTahmin(harf, btn) {
    if (!secilenKelime) return;
    if (btn) btn.disabled = true;
    if (secilenKelime.includes(harf)) {
      dogruHarfler.push(harf);
    } else {
      hataliTahmin++;
      adamCiz(hataliTahmin);
      if (btn) btn.classList.add("wrong");
    }
    guncelleEkran();
  }

  function guncelleEkran() {
    if (!secilenKelime) {
      document.getElementById("hakSayisi").innerText = maxHak;
      document.getElementById("wordDisplay").innerText = "";
      return;
    }
    const display = secilenKelime.split("").map(harf => (dogruHarfler.includes(harf) ? harf : "_")).join(" ");
    document.getElementById("wordDisplay").innerText = display;
    document.getElementById("hakSayisi").innerText = maxHak - hataliTahmin;

    if (!display.includes("_")) {
      document.getElementById("status").innerText = "Tebrikler! Bildiniz.";
      kilitleButonlar();
    } else if (hataliTahmin >= maxHak) {
      document.getElementById("status").innerText = `Oyun bitti! Kelime: ${secilenKelime}`;
      kilitleButonlar();
    }
  }

  function kilitleButonlar() {
    document.querySelectorAll(".letter-btn").forEach(btn => btn.disabled = true);
  }

  function adamCiz(hak) {
    const parcalar = ["svg-head", "svg-body", "svg-arm-left", "svg-arm-right", "svg-leg-left", "svg-leg-right"];
    if (hak <= parcalar.length) {
      const parca = document.getElementById(parcalar[hak - 1]);
      if (parca) parca.style.display = "inline";
    }
  }

  function sifirlaAdamCizimi() {
    ["svg-head", "svg-body", "svg-arm-left", "svg-arm-right", "svg-leg-left", "svg-leg-right"].forEach(id => {
      const eleman = document.getElementById(id);
      if (eleman) eleman.style.display = "none";
    });
  }

  // --- XOX KODLARI ---
  let xoxBoxes, xoxTurn, xoxIsGameOver;

  function xoxInit() {
      xoxBoxes = document.querySelectorAll("#xox-alani .box");
      xoxTurn = "X";
      xoxIsGameOver = false;
      xoxBoxes.forEach(e => {
          e.innerHTML = "";
          e.style.removeProperty("background-color");
          e.style.color = "#fff";
          e.onclick = function() {
              if(!xoxIsGameOver && e.innerHTML === "") {
                  e.innerHTML = xoxTurn;
                  xoxCheakWin();
                  xoxCheakDraw();
                  xoxChangeTurn();
              }
          };
      });
      document.getElementById("xox-results").innerHTML = "";
      document.getElementById("xox-play-again").style.display = "none";
      document.querySelector("#xox-alani .bg").style.left = "0";
  }

  function xoxChangeTurn() {
      if (xoxTurn === "X") {
          xoxTurn = "O";
          document.querySelector("#xox-alani .bg").style.left = "85px";
      } else {
          xoxTurn = "X";
          document.querySelector("#xox-alani .bg").style.left = "0";
      }
  }

  function xoxCheakWin() {
      let winConditions = [[0, 1, 2], [3, 4, 5], [6, 7, 8], [0, 3, 6], [1, 4, 7], [2, 5, 8], [0, 4, 8], [2, 4, 6]];
      for (let i = 0; i < winConditions.length; i++) {
          let v0 = xoxBoxes[winConditions[i][0]].innerHTML;
          let v1 = xoxBoxes[winConditions[i][1]].innerHTML;
          let v2 = xoxBoxes[winConditions[i][2]].innerHTML;
          if (v0 != "" && v0 === v1 && v0 === v2) {
              xoxIsGameOver = true;
              document.getElementById("xox-results").innerHTML = xoxTurn + " kazandı!";
              document.getElementById("xox-play-again").style.display = "inline";
              for (let j = 0; j < 3; j++) {
                  xoxBoxes[winConditions[i][j]].style.backgroundColor = "#08D9D6";
                  xoxBoxes[winConditions[i][j]].style.color = "#000";
              }
          }
      }
  }

  function xoxCheakDraw() {
      if (!xoxIsGameOver) {
          let isDraw = true;
          xoxBoxes.forEach(e => { if (e.innerHTML === "") isDraw = false; });
          if (isDraw) {
              xoxIsGameOver = true;
              document.getElementById("xox-results").innerHTML = "Berabere!";
              document.getElementById("xox-play-again").style.display = "inline";
          }
      }
  }

  function xoxGoster() {
      hideAllGames();
      document.getElementById("xox-alani").style.display = "block";
      xoxInit();
  }

  document.addEventListener("DOMContentLoaded", function() {
      xoxInit();
      document.getElementById("xox-play-again").onclick = xoxInit;
  });

  // --- YILAN OYUNU KODLARI ---
  const canvas = document.getElementById("gameCanvas");
  const ctx = canvas.getContext("2d");
  let snake = [], dx, dy, foodX, foodY, snakeScore = 0, changingDirection = false;
  let gameInterval;
  let isSnakeGameActive = false; // Yılan oyunu açık mı kontrolü

  function snakeGoster() {
    hideAllGames();
    document.getElementById("snake-alani").style.display = "block";
    isSnakeGameActive = true;
    startSnakeGame();
  }

  function startSnakeGame() {
    if(gameInterval) clearInterval(gameInterval);
    snake = [{x: 150, y: 150}, {x: 140, y: 150}, {x: 130, y: 150}, {x: 120, y: 150}, {x: 110, y: 150}];
    snakeScore = 0;
    document.getElementById('snakeScore').innerHTML = snakeScore;
    dx = 10; dy = 0;
    createFood();
    gameInterval = setInterval(mainSnakeLoop, 100);
  }

  function mainSnakeLoop() {
      if (!isSnakeGameActive) { clearInterval(gameInterval); return; }
      if (didGameEnd()) {
          alert("Oyun Bitti! Skorun: " + snakeScore);
          clearInterval(gameInterval);
          return;
      }
      changingDirection = false;
      clearCanvas();
      drawFood();
      advanceSnake();
      drawSnake();
  }

  function clearCanvas() {
      ctx.fillStyle = "#f0f0f0";
      ctx.strokeStyle = "#333";
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      ctx.strokeRect(0, 0, canvas.width, canvas.height);
  }

  function drawSnake() { snake.forEach(drawSnakePart); }
  function drawSnakePart(snakePart) {
      ctx.fillStyle = 'lightgreen';
      ctx.strokeStyle = 'darkgreen';
      ctx.fillRect(snakePart.x, snakePart.y, 10, 10);
      ctx.strokeRect(snakePart.x, snakePart.y, 10, 10);
  }

  function advanceSnake() {
      const head = {x: snake[0].x + dx, y: snake[0].y + dy};
      snake.unshift(head);
      if (snake[0].x === foodX && snake[0].y === foodY) {
          snakeScore += 10;
          document.getElementById('snakeScore').innerHTML = snakeScore;
          createFood();
      } else {
          snake.pop();
      }
  }

  function changeSnakeDirection(dir) {
      if (changingDirection) return;
      changingDirection = true;
      const goingUp = dy === -10;
      const goingDown = dy === 10;
      const goingRight = dx === 10;
      const goingLeft = dx === -10;

      if (dir === 'LEFT' && !goingRight) { dx = -10; dy = 0; }
      if (dir === 'UP' && !goingDown) { dx = 0; dy = -10; }
      if (dir === 'RIGHT' && !goingLeft) { dx = 10; dy = 0; }
      if (dir === 'DOWN' && !goingUp) { dx = 0; dy = 10; }
  }

  function randomTen(min, max) { return Math.round((Math.random() * (max - min) + min) / 10) * 10; }
  function createFood() {
      foodX = randomTen(0, canvas.width - 10);
      foodY = randomTen(0, canvas.height - 10);
      snake.forEach(part => { if (part.x == foodX && part.y == foodY) createFood(); });
  }
  function drawFood() {
      ctx.fillStyle = 'red';
      ctx.strokeStyle = 'darkred';
      ctx.fillRect(foodX, foodY, 10, 10);
      ctx.strokeRect(foodX, foodY, 10, 10);
  }
  function didGameEnd() {
      for (let i = 4; i < snake.length; i++) {
          if (snake[i].x === snake[0].x && snake[i].y === snake[0].y) return true;
      }
      return snake[0].x < 0 || snake[0].x > canvas.width - 10 || snake[0].y < 0 || snake[0].y > canvas.height - 10;
  }

  // --- ORTAK FONKSİYONLAR ---
  function hideAllGames() {
      document.getElementById("oyun-alani").style.display = "none";
      document.getElementById("xox-alani").style.display = "none";
      document.getElementById("snake-alani").style.display = "none";
      isSnakeGameActive = false; // Yılan oyununu arka planda durdur
      if(gameInterval) clearInterval(gameInterval);
  }

  // Klavye dinleyicisi (Hem Adam Asmaca hem Yılan için)
  document.addEventListener("keydown", function(event) {
    // Eğer Yılan oyunu aktifse Yön tuşlarını dinle
    if (isSnakeGameActive) {
        const key = event.keyCode;
        if([37, 38, 39, 40].includes(key)) {
             event.preventDefault(); // Sayfanın kaymasını engelle
             if(key === 37) changeSnakeDirection('LEFT');
             if(key === 38) changeSnakeDirection('UP');
             if(key === 39) changeSnakeDirection('RIGHT');
             if(key === 40) changeSnakeDirection('DOWN');
        }
    }
    // Eğer Adam Asmaca aktifse Harfleri dinle
    else if (document.getElementById("oyun-alani").style.display === "block") {
        if (!secilenKelime) return;
        const harf = event.key.toUpperCase();
        if (harf >= "A" && harf <= "Z") {
            const btn = document.getElementById("btn-" + harf);
            if (btn && !btn.disabled) harfTahmin(harf, btn);
        }
    }
  });

</script>
</body>
</html>
