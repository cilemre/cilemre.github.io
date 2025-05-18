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
    border: 3px solid cyan;           /* Koyu yerine parlayan için 3px cyan border */
    box-shadow: 0px 0px 15px cyan, 0px 0px 15px cyan inset; /* Parlayan efekt */
    border-radius: 12px;              /* Biraz daha yuvarlak köşe (isteğe bağlı) */
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
<style>
  ... <!-- senin mevcut css kodların -->
  
  /* AŞAĞIDAKİ YENİ KODU EN ALTA EKLE */
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
  // Kategori ve kelime-ipucu verileri:
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
  document.getElementById("oyun-alani").style.display = "block";
  // Sadece kategori seçimi gözüksün, diğerleri gizli kalsın
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
  // Rastgele kelime seç
  const havuz = kelimeler[kategori];
  const secim = havuz[Math.floor(Math.random() * havuz.length)];
  secilenKelime = secim.kelime.toUpperCase();
  secilenIpucu = secim.ipucu;
  dogruHarfler = [];
  hataliTahmin = 0;
  // Kategori seçimi ve başlığını gizle, diğerlerini göster
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


function oyunuYenidenBaslat() {
  seciliKategori = "";
  secilenKelime = "";
  secilenIpucu = "";
  dogruHarfler = [];
  hataliTahmin = 0;
  document.getElementById("kategoriSecim").style.display = "flex";
  document.getElementById("kategoriBaslik").style.display = "block"; // YENİ EKLENDİ
  document.getElementById("ipucuAlani").style.display = "none";
  document.getElementById("hakSayisi").innerText = maxHak;
  document.getElementById("wordDisplay").innerText = "";
  document.getElementById("letters").innerHTML = "";
  document.getElementById("status").innerText = "";
  sifirlaAdamCizimi();
}


  function oyunuYenidenBaslat() {
    seciliKategori = "";
    secilenKelime = "";
    secilenIpucu = "";
    dogruHarfler = [];
    hataliTahmin = 0;
    document.getElementById("kategoriSecim").style.display = "flex";
    document.getElementById("ipucuAlani").style.display = "none";
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

  function sifirlaAdamCizimi() {
    ["svg-head", "svg-body", "svg-arm-left", "svg-arm-right", "svg-leg-left", "svg-leg-right"].forEach(id => {
      const eleman = document.getElementById(id);
      if (eleman) eleman.style.display = "none";
    });
  }
</script>
