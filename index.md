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
    left: 20px;
    top: 20px;
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
    padding: 10px;
  }

  .icerik-sol {
    flex: 3;
  }

  .oyunlar-sag {
    flex: 1;
    background-color: #2a2a40;
    padding: 10px;
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
    padding: 10px;
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

  .letter-btn.wrong {
    background-color: #c0392b;
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
  <p><strong>Kalan Hak:</strong> <span id="hakSayisi"></span></p>
  <div id="wordDisplay" class="hangman-word"></div>
  <div id="letters"></div>
  <p id="status"></p>
<div id="svg-hangman-container" style="text-align: center; margin-top: 20px;">
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
  <button onclick="oyunBaslat()" class="btn" style="margin-top: 20px;">Yeniden Başlat</button>
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
  const kelimeler = ["BLOG", "ENERJI", "GAZI", "MUHENDIS", "OTOMOTIV"];
  let secilen = "";
  let dogruHarfler = [];
  let hataliTahmin = 0;
  const maxHak = 6;

  function oyunGoster() {
    document.getElementById("oyun-alani").style.display = "block";
    oyunBaslat();
  }

  function oyunBaslat() {
  ["svg-head", "svg-body", "svg-arm-left", "svg-arm-right", "svg-leg-left", "svg-leg-right"].forEach(id => {
    const eleman = document.getElementById(id);
    if (eleman) eleman.style.display = "none";
  });
    secilen = kelimeler[Math.floor(Math.random() * kelimeler.length)];
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
      adamCiz(hataliTahmin);
      if (btn) btn.classList.add("wrong");
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

function adamCiz(hak) {
  const parcalar = [
    "svg-head",
    "svg-body",
    "svg-arm-left",
    "svg-arm-right",
    "svg-leg-left",
    "svg-leg-right"
  ];
  if (hak <= parcalar.length) {
    const parca = document.getElementById(parcalar[hak - 1]);
    if (parca) parca.style.display = "inline";
  }
}

</script>
