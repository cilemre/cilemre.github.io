
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Emre Çil - Kişisel Sayfa</title>
  <link rel="icon" type="image/x-icon" href="favicon.ico">
  <style>
      .glow-btn {
        position: relative;
        z-index: 0;
        overflow: hidden;
        transition: 0.4s ease-in-out;
        box-shadow: 0 0 5px #00e6e6, 0 0 10px #00e6e6;
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

      @media (max-width: 768px) {
        .profil-foto {
          position: static;
          display: block;
          margin: 20px auto;
        }
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

      .oyunlar-sag h3 {
        color: #7cc6fe;
        margin-top: 0;
      }

      .oyunlar-sag ul {
        list-style: none;
        padding: 0;
        margin: 0;
      }

      .oyunlar-sag li { margin-bottom: 10px; }

      .oyunlar-sag a {
        color: #e0e0e0;
        text-decoration: none;
        cursor: pointer;
      }

      .oyunlar-sag a:hover { text-decoration: underline; }

      .oyun-alani {
        margin-top: 60px;
        display: none;
        padding: 20px;
        border: 3px solid cyan;
        box-shadow: 0px 0px 15px cyan, 0px 0px 15px cyan inset;
        border-radius: 12px;
        background-color: #292940;
      }

      .hangman-word {
        letter-spacing: 10px;
        font-size: 24px;
        margin-bottom: 20px;
      }

      .letter-btn {
        padding: 8px 12px;
        margin: 4px;
        font-size: 16px;
        border-radius: 5px;
        background-color: #444;
        color: #fff;
        border: none;
        cursor: pointer;
      }

      .letter-btn.wrong { background-color: #c0392b; }

      .kategori-secim {
        display: flex;
        justify-content: center;
        gap: 20px;
        margin: 20px 0 30px 0;
      }

      .ipucu {
        background-color: #44476a;
        color: #fff;
        padding: 8px 16px;
        border-radius: 6px;
        font-size: 16px;
        margin-bottom: 18px;
        display: inline-block;
      }

      /* XOX Stilleri */
      .align {
        display: flex;
        justify-content: center;
        align-items: center;
      }

      .turn-container {
        width: 170px;
        height: 80px;
        margin: auto;
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr 1fr;
        position: relative;
      }

      .turn-container h3 {
        margin: 0;
        grid-column-start: 1;
        grid-column-end: 3;
      }

      .turn-container .turn-box {
        border: 3px solid #7cc6fe;
        font-size: 1.6rem;
        font-weight: 700;
        background-color: #444;
        transition: transform 0.2s ease, box-shadow 0.2s ease;
      }

      .turn-container .turn-box.active {
        transform: scale(1.1);
        box-shadow: 0 0 10px #00e6e6;
      }

      .turn-container .turn-box:nth-child(even) {
        border-right: none;
      }

      .bg {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 85px;
        height: 40px;
        background-color: #00e6e6;
        z-index: -1;
        transition: left 0.3s ease;
      }

      .main-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 1fr);
        height: 250px;
        width: 250px;
        margin: 30px auto;
        border: 2px solid #7cc6fe;
      }

      .box {
        cursor: pointer;
        font-size: 2rem;
        font-weight: 700;
        border: 2px solid #7cc6fe;
        background-color: #444;
      }

      .box:hover {
        background-color: #5fb2ec;
      }

      #xox-results {
        text-align: center;
      }

      #xox-play-again {
        background-color: #7cc6fe;
        padding: 10px 25px;
        border: none;
        font-size: 1.2rem;
        border-radius: 5px;
        cursor: pointer;
        display: none;
        color: #1e1e2f;
        font-weight: 600;
      }

      #xox-play-again:hover {
        background-color: #5fb2ec;
      }

      #xox-selection {
        text-align: center;
        margin: 20px 0;
        display: none;
      }

      #xox-selection p {
        font-size: 1.2rem;
        margin-bottom: 20px;
      }

      #xox-selection button {
        margin: 0 10px;
        padding: 10px 20px;
        font-size: 1.2rem;
      }

      @media (max-width: 768px) {
        .icerik-kapsayici {
          flex-direction: column;
          padding: 10px;
          gap: 10px;
        }

        .profil-foto { width: 80px; }

        .btn {
          min-width: 100px;
          font-size: 13px;
          padding: 5px 10px;
        }

        .oyun-alani { padding: 10px; }

        .hangman-word {
          letter-spacing: 6px;
          font-size: 18px;
        }

        #svg-hangman-container svg {
          width: 150px;
          height: auto;
        }

        .letter-btn {
          padding: 6px 10px;
          font-size: 14px;
        }

        .oyunlar-sag { margin-top: 30px; }

        .main-grid {
          height: 200px;
          width: 200px;
        }

        .box {
          font-size: 1.8rem;
        }

        .turn-container {
          width: 140px;
          height: 70px;
        }

        .turn-container .turn-box {
          font-size: 1.4rem;
        }

        .bg {
          width: 70px;
          height: 35px;
        }

        #xox-play-again {
          padding: 8px 20px;
          font-size: 1rem;
        }

        #xox-selection button {
          padding: 8px 15px;
          font-size: 1rem;
        }
      }

      h1 {
        font-size: 28px;
        margin-bottom: 10px;
      }

      @media (max-width: 768px) {
        h1 { font-size: 22px; }
      }
  </style>
</head>
<body>
  <img src="profil.jpeg" alt="Profil Fotoğrafı" class="profil-foto">
  <div class="icerik-kapsayici">
    <div class="icerik-sol">
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
      <div class="oyun-alani" id="xox-alani">
        <h2>XOX</h2>
        <div id="xox-selection">
          <p>Hangi sembolü seçmek istersin?</p>
          <button class="btn glow-btn" onclick="startXox('X')">X</button>
          <button class="btn glow-btn" onclick="startXox('O')">O</button>
        </div>
        <div id="xox-game" style="display:none;">
          <div class="turn-container">
            <h3>Sıra</h3>
            <div class="turn-box align" id="turn-x">X</div>
            <div class="turn-box align" id="turn-o">O</div>
            <div class="bg"></div>
          </div>
          <div class="main-grid">
            <div class="box align" id="0"></div>
            <div class="box align" id="1"></div>
            <div class="box align" id="2"></div>
            <div class="box align" id="3"></div>
            <div class="box align" id="4"></div>
            <div class="box align" id="5"></div>
            <div class="box align" id="6"></div>
            <div class="box align" id="7"></div>
            <div class="box align" id="8"></div>
          </div>
          <h2 id="xox-results"></h2>
          <button id="xox-play-again" class="btn glow-btn" style="display:none;">Tekrar Oyna</button>
        </div>
      </div>
      <hr>
      <p style="text-align: center; margin-top: 40px; font-size: 14px; color: #999;">
        İletişim için: <strong>emre.cil@gazi.edu.tr</strong>
      </p>
    </div>
    <aside class="oyunlar-sag">
      <h3>🎮 Oyunlar</h3>
      <ul>
        <li><a id="adam-asmaca-link" onclick="oyunGoster()">Adam Asmaca</a></li>
        <li><a id="xox-link" onclick="xoxGoster()">XOX</a></li>
      </ul>
    </aside>
  </div>

  <script>
    // Adam Asmaca Kodları
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
    let secilenIpucu = "";
    let seciliKategori = "";
    let dogruHarfler = [];
    let hataliTahmin = 0;
    const maxHak = 6;

    function oyunGoster() {
      console.log("Adam Asmaca gösteriliyor"); // Hata ayıklama
      document.getElementById("oyun-alani").style.display = "block";
      document.getElementById("xox-alani").style.display = "none";
      document.getElementById("kategoriSecim").style.display = "flex";
      document.getElementById("kategoriBaslik").style.display = "block";
      document.getElementById("ipucuAlani").style.display = "none";
      document.getElementById("hakSatiri").style.display = "none";
      document.getElementById("wordDisplay").style.display = "none";
      document.getElementById("letters").style.display = "none";
      document.getElementById("status").style.display = "none";
      document.getElementById("svg-hangman-container").style.display = "none";
      document.getElementById("yenidenBaslatBtn").style.display = "none";
    }

    function kategoriSec(kategori) {
      seciliKategori = kategori;
      const havuz = kelimeler[kategori];
      const secim = havuz[Math.floor(Math.random() * havuz.length)];
      secilenKelime = secim.kelime.toUpperCase();
      secilenIpucu = secim.ipucu;
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
      seciliKategori = "";
      secilenKelime = "";
      secilenIpucu = "";
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
      document.getElementById("status").innerText = "";
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

    document.addEventListener("keydown", function(event) {
      if (!secilenKelime) return;
      const harf = event.key.toUpperCase();
      if (harf >= "A" && harf <= "Z") {
        const btn = document.getElementById("btn-" + harf);
        if (btn && !btn.disabled) {
          harfTahmin(harf, btn);
        }
      }
    });

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

    // XOX Oyunu Kodları
    let xoxBoxes = document.querySelectorAll("#xox-alani .box");
    let xoxTurn = "X"; // X her zaman başlar
    let xoxIsGameOver = false;
    let playerSymbol = null; // Oyuncunun seçtiği sembol (X veya O)
    let botSymbol = null; // Botun sembolü

    function xoxGoster() {
      console.log("XOX gösteriliyor"); // Hata ayıklama
      document.getElementById("oyun-alani").style.display = "none";
      document.getElementById("xox-alani").style.display = "block";
      document.getElementById("xox-selection").style.display = "block";
      document.getElementById("xox-game").style.display = "none";
      xoxReset();
    }

    function startXox(symbol) {
      playerSymbol = symbol;
      botSymbol = symbol === "X" ? "O" : "X";
      document.getElementById("xox-selection").style.display = "none";
      document.getElementById("xox-game").style.display = "block";
      xoxInit();
      if (playerSymbol === "O") {
        setTimeout(botMove, 500); // Bot X ile başlar
      }
    }

    function xoxReset() {
      playerSymbol = null;
      botSymbol = null;
      xoxInit();
    }

    function xoxInit() {
      xoxTurn = "X"; // X her zaman başlar
      xoxIsGameOver = false;
      xoxBoxes.forEach(e => {
        e.innerHTML = "";
        e.style.backgroundColor = "";
        e.style.color = "#fff";
      });
      document.querySelector("#xox-results").innerHTML = "";
      document.querySelector("#xox-play-again").style.display = "none";
      document.querySelector("#xox-alani .bg").style.left = xoxTurn === "X" ? "0" : "85px";
      document.querySelector("#turn-x").classList.toggle("active", xoxTurn === "X");
      document.querySelector("#turn-o").classList.toggle("active", xoxTurn === "O");
      document.querySelector(".main-grid").style.pointerEvents = "auto"; // Tahta tıklanabilir
    }

    function handleBoxClick(event) {
      const box = event.target;
      if (!xoxIsGameOver && box.innerHTML === "" && xoxTurn === playerSymbol) {
        box.innerHTML = playerSymbol;
        xoxCheakWin();
        xoxCheckEarlyDraw();
        xoxCheakDraw();
        xoxChangeTurn();
        if (!xoxIsGameOver && xoxTurn === botSymbol) {
          setTimeout(botMove, 500);
        }
      }
    }

    function xoxChangeTurn() {
      xoxTurn = xoxTurn === "X" ? "O" : "X";
      document.querySelector("#xox-alani .bg").style.left = xoxTurn === "X" ? "0" : "85px";
      document.querySelector("#turn-x").classList.toggle("active", xoxTurn === "X");
      document.querySelector("#turn-o").classList.toggle("active", xoxTurn === "O");
    }

    function xoxCheakWin() {
      let winConditions = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8],
        [0, 3, 6], [1, 4, 7], [2, 5, 8],
        [0, 4, 8], [2, 4, 6]
      ];
      for (let i = 0; i < winConditions.length; i++) {
        let v0 = xoxBoxes[winConditions[i][0]].innerHTML;
        let v1 = xoxBoxes[winConditions[i][1]].innerHTML;
        let v2 = xoxBoxes[winConditions[i][2]].innerHTML;
        if (v0 !== "" && v0 === v1 && v0 === v2) {
          xoxIsGameOver = true;
          document.querySelector("#xox-results").innerHTML = v0 + " kazandı!";
          document.querySelector("#xox-play-again").style.display = "inline";
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
        xoxBoxes.forEach(e => {
          if (e.innerHTML === "") isDraw = false;
        });
        if (isDraw) {
          xoxIsGameOver = true;
          document.querySelector("#xox-results").innerHTML = "Berabere!";
          document.querySelector("#xox-play-again").style.display = "inline";
          document.querySelector(".main-grid").style.pointerEvents = "auto"; // Tahta tıklanabilir kalır
        }
      }
    }

    function xoxCheckEarlyDraw() {
      if (xoxIsGameOver) return;
      let winConditions = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8],
        [0, 3, 6], [1, 4, 7], [2, 5, 8],
        [0, 4, 8], [2, 4, 6]
      ];
      let canXWin = false;
      let canOWin = false;
      for (let i = 0; i < winConditions.length; i++) {
        let [a, b, c] = winConditions[i];
        let values = [xoxBoxes[a].innerHTML, xoxBoxes[b].innerHTML, xoxBoxes[c].innerHTML];
        let xCount = values.filter(v => v === "X").length;
        let oCount = values.filter(v => v === "O").length;
        let emptyCount = values.filter(v => v === "").length;
        if (emptyCount > 0) {
          if (xCount === 0 && oCount === 0) {
            canXWin = true;
            canOWin = true;
          } else if (xCount > 0 && oCount === 0) {
            canXWin = true;
          } else if (oCount > 0 && xCount === 0) {
            canOWin = true;
          }
        }
      }
      if (!canXWin && !canOWin) {
        xoxIsGameOver = true;
        document.querySelector("#xox-results").innerHTML = "Berabere!";
        document.querySelector("#xox-play-again").style.display = "inline";
        document.querySelector(".main-grid").style.pointerEvents = "auto"; // Tahta tıklanabilir kalır
      }
    }

    function botMove() {
      if (xoxIsGameOver) return;

      let winMove = findWinningMove(botSymbol);
      if (winMove !== -1) {
        xoxBoxes[winMove].innerHTML = botSymbol;
        xoxCheakWin();
        xoxCheckEarlyDraw();
        xoxCheakDraw();
        xoxChangeTurn();
        return;
      }

      let blockMove = findWinningMove(playerSymbol);
      if (blockMove !== -1) {
        xoxBoxes[blockMove].innerHTML = botSymbol;
        xoxCheakWin();
        xoxCheckEarlyDraw();
        xoxCheakDraw();
        xoxChangeTurn();
        return;
      }

      if (xoxBoxes[4].innerHTML === "") {
        xoxBoxes[4].innerHTML = botSymbol;
        xoxCheakWin();
        xoxCheckEarlyDraw();
        xoxCheakDraw();
        xoxChangeTurn();
        return;
      }

      const corners = [0, 2, 6, 8];
      let emptyCorners = corners.filter(i => xoxBoxes[i].innerHTML === "");
      if (emptyCorners.length > 0) {
        let randomCorner = emptyCorners[Math.floor(Math.random() * emptyCorners.length)];
        xoxBoxes[randomCorner].innerHTML = botSymbol;
        xoxCheakWin();
        xoxCheckEarlyDraw();
        xoxCheakDraw();
        xoxChangeTurn();
        return;
      }

      let emptyBoxes = Array.from(xoxBoxes).filter(e => e.innerHTML === "");
      if (emptyBoxes.length > 0) {
        let randomBox = emptyBoxes[Math.floor(Math.random() * emptyBoxes.length)];
        randomBox.innerHTML = botSymbol;
        xoxCheakWin();
        xoxCheckEarlyDraw();
        xoxCheakDraw();
        xoxChangeTurn();
      }
    }

    function findWinningMove(player) {
      let winConditions = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8],
        [0, 3, 6], [1, 4, 7], [2, 5, 8],
        [0, 4, 8], [2, 4, 6]
      ];
      for (let i = 0; i < winConditions.length; i++) {
        let [a, b, c] = winConditions[i];
        let va = xoxBoxes[a].innerHTML;
        let vb = xoxBoxes[b].innerHTML;
        let vc = xoxBoxes[c].innerHTML;
        if (va === player && vb === player && vc === "") return c;
        if (va === player && vc === player && vb === "") return b;
        if (vb === player && vc === player && va === "") return a;
      }
      return -1;
    }

    document.querySelector("#xox-play-again").addEventListener("click", () => {
      xoxGoster();
    });

    xoxBoxes.forEach(e => {
      e.addEventListener("click", handleBoxClick);
    });

    // Oyun bağlantılarına dinamik olay dinleyicileri ekle
    document.getElementById("adam-asmaca-link").addEventListener("click", oyunGoster);
    document.getElementById("xox-link").addEventListener("click", xoxGoster);

    // Sayfa yüklendiğinde oyun alanlarını gizle
    document.getElementById("oyun-alani").style.display = "none";
    document.getElementById("xox-alani").style.display = "none";
  </script>
</body>
</html>
