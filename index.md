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
  }

  .btn:hover {
    background-color: #5fb2ec;
  }

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
    gap: 40px;
    padding: 40px;
  }

  .icerik-sol {
    flex: 3;
  }

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

  .oyunlar-sag li {
    margin-bottom: 10px;
  }

  .oyunlar-sag a {
    color: #e0e0e0;
    text-decoration: none;
    cursor: pointer;
  }

  .oyunlar-sag a:hover {
    text-decoration: underline;
  }

  .oyun-alani {
    margin-top: 60px;
    display: none;
    padding: 20px;
    border: 1px solid #555;
    border-radius: 10px;
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
      <p><strong>Kalan Hak:</strong> <span id="hakSayisi"></span></p>
      <div id="wordDisplay" class="hangman-word"></div>
      <div id="letters"></div>
      <p id="status"></p>
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
  const kelimeler = ["blog", "enerji", "gazi", "mühendis", "otomotiv"];
  let secilen = "";
  let dogruHarfler = [];
  let hataliTahmin = 0;
  const maxHak = 6;

  function oyunGoster() {
    document.getElementById("oyun-alani").style.display = "block";
    oyunBaslat();
  }

  function oyunBaslat() {
    secilen = kelimeler[Math.floor(Math.random() * kelimeler.length)].toUpperCase();
    dogruHarfler = [];
    hataliTahmin = 0;
    document.getElementById("status").innerText = "";
    harfleriOlustur();
    guncelleEkran();
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
    if (btn) btn.disabled = true;
    if (secilen.includes(harf)) {
      dogruHarfler.push(harf);
    } else {
      hataliTahmin++;
    }
    guncelleEkran();
  }

  function guncelleEkran() {
    const display = secilen.split("").map(harf => (dogruHarfler.includes(harf) ? harf : "_")).join(" ");
    document.getElementById("wordDisplay").innerText = display;
    document.getElementById("hakSayisi").innerText = maxHak - hataliTahmin;

    if (!display.includes("_")) {
      document.getElementById("status").innerText = "Tebrikler! Bildiniz.";
      kilitleButonlar();
    } else if (hataliTahmin >= maxHak) {
      document.getElementById("status").innerText = `Oyun bitti! Kelime: ${secilen}`;
      kilitleButonlar();
    }
  }

  function kilitleButonlar() {
    document.querySelectorAll(".letter-btn").forEach(btn => btn.disabled = true);
  }

  document.addEventListener("keydown", function(event) {
    const harf = event.key.toUpperCase();
    if (harf >= "A" && harf <= "Z") {
      const btn = document.getElementById("btn-" + harf);
      if (btn && !btn.disabled) {
        harfTahmin(harf, btn);
      }
    }
  });
</script>
