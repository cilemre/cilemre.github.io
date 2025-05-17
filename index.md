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
    gap: 20px;
    padding: 20px;
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


<div id="kategori-secimi" style="display: none; text-align:center; margin-top:20px;" style="text-align:center; margin-top:20px;">
  <h3 style="margin-bottom: 10px;">Kategori Seç:</h3>
  <button class="btn" onclick="kategoriSec('film')">🎬 Film</button>
  <button class="btn" onclick="kategoriSec('muhendislik')">⚙️ Mühendislik</button>
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
const kelimeListesi = {
  film: [
    { kelime: "INCEPTION", ipucu: "Rüya içinde rüya konusunu işleyen bilim kurgu filmi" },
    { kelime: "INTERSTELLAR", ipucu: "Kara delik ve zaman yolculuğu temalı uzay filmi" },
    { kelime: "TITANIC", ipucu: "Gerçek bir gemi kazasına dayanan romantik film" },
    { kelime: "MATRIX", ipucu: "Gerçeklik ve simülasyon üzerine felsefi film" },
    { kelime: "AVATAR", ipucu: "Mavi tenli yaratıkların yaşadığı gezegen" },
    { kelime: "GLADIATOR", ipucu: "Roma İmparatorluğu döneminde geçen bir intikam filmi" },
    { kelime: "JOKER", ipucu: "Gotham'ın meşhur kötü karakteri" },
    { kelime: "BATMAN", ipucu: "Özel gücü olmayan multimilyoner süper kahraman" },
    { kelime: "GODFATHER", ipucu: "Mafya dünyasında geçen efsanevi bir film serisi" },
    { kelime: "PARASITE", ipucu: "Güney Kore yapımı, sınıf ayrımını anlatan film" },
    { kelime: "DUNE", ipucu: "Çöl gezegeninde geçen bir bilim kurgu destanı" },
    { kelime: "FIGHTCLUB", ipucu: "İlk kuralı, hakkında konuşmamaktır." },
    { kelime: "FORRESTGUMP", ipucu: "Başrolde Tom Hanks'in oynadığı Oscar'lı film." },
    { kelime: "AVENGERS", ipucu: "Süper kahramanların bir araya geldiği Marvel filmi" },
    { kelime: "DEADPOOL", ipucu: "Alaycı ve esprili bir süper kahraman" },
    { kelime: "FROZEN", ipucu: "Buz büyüleri yapan prensesin hikayesi" },
    { kelime: "UP", ipucu: "Balonlarla uçan bir evin macerası" },
    { kelime: "HARRYPOTTER", ipucu: "Büyücülük okulunda okuyan çocuk" },
    { kelime: "STARWARS", ipucu: "Işın kılıçları ve galaktik savaşlar" },
    { kelime: "SHREK", ipucu: "Bataklıkta yaşayan yakın arkadaşı eşek olan karakter" }
  ],
  muhendislik: [
    { kelime: "TERMODINAMIK", ipucu: "Isı, enerji ve dengeyle ilgilenen mühendislik dalı" },
    { kelime: "TURBIN", ipucu: "Dönme hareketiyle elektrik üreten makine" },
    { kelime: "GUNESENERJISI", ipucu: "Yenilenebilir, fotovoltaik panellerle elde edilir" },
    { kelime: "AKISKANLAR", ipucu: "Gaz ve sıvıların davranışlarını inceleyen mühendislik konusu" },
    { kelime: "VERIM", ipucu: "Girdiye göre çıktının oranını belirten kavram" },
    { kelime: "RADYATOR", ipucu: "Isı yaymak için kullanılan cihaz" },
    { kelime: "JEOTERMAL", ipucu: "Yerin altındaki ısıdan faydalanan enerji türü" },
    { kelime: "ENTALPI", ipucu: "Termodinamikte toplam enerji ölçütü" },
    { kelime: "DIRENC", ipucu: "Elektrik akımına karşı koyan devre elemanı" },
    { kelime: "BATARYA", ipucu: "Elektrik enerjisini kimyasal olarak depolar" },
    { kelime: "KINETIKENERJI", ipucu: "Hareket halindeki cisimlerin enerjisi" },
    { kelime: "ISIPOMPASI", ipucu: "Isı transferi için kullanılan cihaz" },
    { kelime: "FREKANS", ipucu: "Bir olayın birim zamanda tekrar sayısı" },
    { kelime: "VOLTAJ", ipucu: "Elektrik potansiyel farkı" },
    { kelime: "OTOMASYON", ipucu: "İnsan müdahalesi olmadan sistemlerin çalışması" },
    { kelime: "STATIK", ipucu: "Duran sistemlerdeki kuvvet dengesiyle ilgilenir" },
    { kelime: "ENTROPI", ipucu: "Düzensizliğin ölçüsü, termodinamiğin temel kavramı" }
  ]
};

let secilenKelime = "";
let dogruHarfler = [];
let hataliTahmin = 0;
const maxHak = 6;



  const secim = liste[Math.floor(Math.random() * liste.length)];
  secilenKelime = secim.kelime;
  document.getElementById("oyun-alani").style.display = "block";
  document.getElementById("ipucu")?.remove();
  const ipucuParagraf = document.createElement("p");
  ipucuParagraf.id = "ipucu";
  ipucuParagraf.innerHTML = "<strong>İpucu:</strong> " + secim.ipucu;
  document.getElementById("oyun-alani").insertBefore(ipucuParagraf, document.getElementById("wordDisplay"));

  dogruHarfler = [];
  hataliTahmin = 0;
  document.getElementById("status").innerText = "";
  harfleriOlustur();
  guncelleEkran();
}


function oyunGoster() {
  document.getElementById("kategori-secimi").style.display = "block";
}

function kategoriSec(kategori) {
  document.getElementById("kategori-secimi").style.display = "none";
  const liste = kelimeListesi[kategori];
  const secim = liste[Math.floor(Math.random() * liste.length)];
  secilenKelime = secim.kelime;
  document.getElementById("oyun-alani").style.display = "block";
  document.getElementById("ipucu")?.remove();
  const ipucuParagraf = document.createElement("p");
  ipucuParagraf.id = "ipucu";
  ipucuParagraf.innerHTML = "<strong>İpucu:</strong> " + secim.ipucu;
  document.getElementById("oyun-alani").insertBefore(ipucuParagraf, document.getElementById("wordDisplay"));

  dogruHarfler = [];
  hataliTahmin = 0;
  document.getElementById("status").innerText = "";
  harfleriOlustur();
  guncelleEkran();
}


function oyunBaslat() {
  location.reload();
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
  const display = secilenKelime.split("").map(harf => (dogruHarfler.includes(harf) ? harf : "_")).join(" ");
  document.getElementById("wordDisplay").innerText = display;
  document.getElementById("hakSayisi").innerText = maxHak - hataliTahmin;

  if (!display.includes("_")) {
    document.getElementById("status").innerText = "🎉 Tebrikler! Bildiniz.";
    kilitleButonlar();
  } else if (hataliTahmin >= maxHak) {
    document.getElementById("status").innerText = `😢 Oyun bitti! Kelime: ${secilenKelime}`;
    kilitleButonlar();
  }
}

function kilitleButonlar() {
  document.querySelectorAll(".letter-btn").forEach(btn => btn.disabled = true);
}

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
