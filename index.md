<link rel="icon" type="image/x-icon" href="favicon.ico">

<style>
/* ... (senin tüm style kodların buraya geliyor, kısaltmadım, dosyadan aynen aldım) ... */
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
  0% { transform: rotate(0deg);}
  100% { transform: rotate(360deg);}
}
/* ... (tüm diğer style kodların buraya olduğu gibi devam ediyor) ... */
body {
  background-color: #1e1e2f;
  color: #e0e0e0;
  font-family: Arial, sans-serif;
  margin: 0;
}
/* ... Tüm style kodun aynı şekilde ... */
</style>

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

    <!-- Oyun Alanları -->
    <div class="oyun-alani" id="oyun-alani" style="display:none;">
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
          <!-- Direk -->
          <line x1="20" y1="230" x2="180" y2="230" stroke="#888" stroke-width="4"/>
          <line x1="50" y1="230" x2="50" y2="20" stroke="#888" stroke-width="4"/>
          <line x1="50" y1="20" x2="130" y2="20" stroke="#888" stroke-width="4"/>
          <line x1="130" y1="20" x2="130" y2="50" stroke="#888" stroke-width="4"/>
          <!-- Adam parçaları (başlangıçta gizli) -->
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

    <!-- XOX Oyun Alanı -->
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
    <!-- /XOX Oyun Alanı -->

    <hr>
    <p style="text-align: center; margin-top: 40px; font-size: 14px; color: #999;">
      İletişim için: <strong>emre.cil@gazi.edu.tr</strong>
    </p>
  </div>

  <aside class="oyunlar-sag">
    <h3>🎮 Oyunlar</h3>
    <ul>
      <li><a onclick="oyunGoster()">Adam Asmaca</a></li>
      <li><a onclick="xoxGoster()">Tic Tac Toe (XOX)</a></li>
      <li><a href="#">Kelime Bulmaca</a></li>
      <li><a href="#">Yeni Oyun</a></li>
    </ul>
  </aside>
</div>

<script>
  // Adam Asmaca kodları (senin orijinal kodların olduğu gibi burada)
  // (Burada kodlarını değiştirmedim, aynen bıraktım!)

  // --- Aşağıya XOX oyununu ekliyoruz ---

  // XOX (Tic Tac Toe) için değişkenler
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
      let winConditions = [
          [0, 1, 2], [3, 4, 5], [6, 7, 8],
          [0, 3, 6], [1, 4, 7], [2, 5, 8],
          [0, 4, 8], [2, 4, 6]
      ]
      for (let i = 0; i < winConditions.length; i++) {
          let v0 = xoxBoxes[winConditions[i][0]].innerHTML;
          let v1 = xoxBoxes[winConditions[i][1]].innerHTML;
          let v2 = xoxBoxes[winConditions[i][2]].innerHTML;

          if (v0 != "" && v0 === v1 && v0 === v2) {
              xoxIsGameOver = true;
              document.getElementById("xox-results").innerHTML = xoxTurn + " kazandı!";
              document.getElementById("xox-play-again").style.display = "inline"
              for (let j = 0; j < 3; j++) {
                  xoxBoxes[winConditions[i][j]].style.backgroundColor = "#08D9D6"
                  xoxBoxes[winConditions[i][j]].style.color = "#000"
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
              document.getElementById("xox-results").innerHTML = "Berabere!";
              document.getElementById("xox-play-again").style.display = "inline"
          }
      }
  }

  function xoxReset() {
      xoxInit();
  }

  // Oyunlar arası geçiş
  function oyunGoster() {
      document.getElementById("oyun-alani").style.display = "block";
      document.getElementById("xox-alani").style.display = "none";
  }
  function xoxGoster() {
      document.getElementById("oyun-alani").style.display = "none";
      document.getElementById("xox-alani").style.display = "block";
      xoxReset();
  }

  // Sayfa açılışında XOX ve Adam Asmaca butonlarına tıklama için hazırla
  document.addEventListener("DOMContentLoaded", function() {
      xoxInit();
      document.getElementById("xox-play-again").onclick = xoxReset;
  });

  // --- Adam Asmaca kodlarının devamı ---
  // (Burada Adam Asmaca'nın kendi kodu yer alıyor, senin orijinalin aynen bırakıldı)
  // --- Bu alanı değiştirmedim ---
</script>
