<link rel="icon" type="image/x-icon" href="favicon.ico">

<style>
  body {
    background-color: #1e1e2f;
    color: #e0e0e0;
    font-family: Arial, sans-serif;
    margin: 0;
  }

  a {
    color: #7cc6fe;
  }

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
    border: none;
    transition: 0.3s;
  }

  .btn:hover {
    background-color: #5fb2ec;
  }

  /* --- ANİMASYONLU MODERN BUTON EFEKTİ --- */
  button.btn-anim {
    height: 48px;
    min-width: 130px;
    border-radius: 24px;
    padding: 0 30px;
    font-size: 16px;
    font-weight: 600;
    text-transform: uppercase;
    color: #fff;
    background: linear-gradient(90deg, #03a9f4, #f441a5, #ffeb3b, #03a9f4);
    background-size: 400%;
    border: none;
    outline: none;
    cursor: pointer;
    position: relative;
    box-sizing: border-box;
    transition: 0.4s;
    z-index: 1;
    letter-spacing: 1px;
    margin: 4px;
    margin-bottom: 8px;
    box-shadow: 0 2px 16px rgba(3,169,244,0.13);
    overflow: hidden;
  }
  button.btn-anim:hover {
    animation: animate 6s linear infinite;
  }
  button.btn-anim:before {
    content: '';
    position: absolute;
    top: -7px;
    left: -7px;
    right: -7px;
    bottom: -7px;
    z-index: -1;
    background: linear-gradient(90deg, #03a9f4, #f441a5, #ffeb3b, #03a9f4);
    background-size: 400%;
    border-radius: 32px;
    opacity: 0;
    transition: 1s;
  }
  button.btn-anim:hover:before {
    filter: blur(16px);
    opacity: 1;
    animation: animate 6s linear infinite;
  }
  @keyframes animate {
    0% { background-position: 0%; }
    100% { background-position: 400%; }
  }

  /* --- GLOWING BORDER KUTU EFEKTİ --- */
  .oyun-alani {
    margin-top: 60px;
    display: none;
    padding: 20px;
    border: 3px solid cyan; /* Parlayan kenarlık */
    box-shadow: 0px 0px 15px cyan, 0px 0px 15px cyan inset;
    border-radius: 12px;
    background-color: #292940;
    transition: 0.4s;
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
  .letter-btn.wrong {
    background-color: #c0392b;
  }

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

  @media (max-width: 768px) {
    .icerik-kapsayici {
      flex-direction: column;
      padding: 10px;
      gap: 10px;
    }
    .profil-foto {
      width: 80px;
    }
    .btn {
      min-width: 100px;
      font-size: 13px;
      padding: 5px 10px;
    }
    .oyun-alani {
      padding: 10px;
    }
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
    .oyunlar-sag {
      margin-top: 30px;
    }
  }
  h1 {
    font-size: 28px;
    margin-bottom: 10px;
  }
  @media (max-width: 768px) {
    h1 {
      font-size: 22px;
    }
  }
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

    <div class="oyun-alani" id="oyun-alani">
      <h2 id="oyun-baslik">Adam Asmaca</h2>
      <div id="kategoriBaslik" style="text-align: center; font-size: 17px; margin-bottom: 8px;">Kategori Seçiniz:</div>
      <div id="kategoriSecim" class="kategori-secim">
        <button class="btn btn-anim" onclick="kategoriSec('muhendislik')">Mühendislik</button>
        <button class="btn btn-anim" onclick="kategoriSec('film')">Film</button>
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
      <button id="yenidenBaslatBtn" onclick="oyunuYenidenBaslat()" class="btn btn-anim" style="margin-top: 20px; display: none;">Yeniden Başlat</button>
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
      <li><a href="#">Kelime Bulmaca</a></li>
      <li><a href="#">Yeni Oyun</a></li>
    </ul>
  </aside>
</div>

<script>
// --- JavaScript kodların aynen burada devam edecek ---
</script>
