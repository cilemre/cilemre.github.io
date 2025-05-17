<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Emre'nin Blogu - Adam Asmaca</title>
  <style>
    body {
      background-color: #1e1e2f;
      color: #e0e0e0;
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
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
      border: none;
      cursor: pointer;
    }
    .btn:hover {
      background-color: #5fb2ec;
    }
    .oyun-alani {
      margin-top: 20px;
      padding: 20px;
      border: 1px solid #555;
      border-radius: 10px;
      background-color: #292940;
      display: none;
    }
    .hangman-word {
      letter-spacing: 10px;
      font-size: 24px;
      margin: 20px 0;
      text-align: center;
    }
    #letters {
      text-align: center;
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
  </style>
</head>
<body>

<h1 style="text-align:center;">🎮 Adam Asmaca</h1>

<div id="kategori-secimi" style="text-align:center; margin-top:20px;">
  <h3>Kategori Seç:</h3>
  <button class="btn" onclick="kategoriSec('film')">🎬 Film</button>
  <button class="btn" onclick="kategoriSec('muhendislik')">⚙️ Mühendislik</button>
</div>

<div class="oyun-alani" id="oyun-alani">
  <p><strong>Kalan Hak:</strong> <span id="hakSayisi"></span></p>
  <p><strong>İpucu:</strong> <span id="ipucu"></span></p>
  <div id="wordDisplay" class="hangman-word"></div>
  <div id="letters"></div>
  <p id="status" style="text-align:center;"></p>
  <button onclick="oyunBaslat()" class="btn">Yeniden Başlat</button>
</div>

<script>
const kelimeListesi = {
  film: [
    { kelime: "INCEPTION", ipucu: "Rüya içinde rüya konusunu işleyen bilim kurgu filmi" },
    { kelime: "TITANIC", ipucu: "Gerçek bir gemi kazasına dayanan romantik film" }
  ],
  muhendislik: [
    { kelime: "TERMODINAMIK", ipucu: "Isı, enerji ve dengeyle ilgilenen mühendislik dalı" },
    { kelime: "VOLTAJ", ipucu: "Elektrik potansiyel farkı" }
  ]
};

let secilenKelime = "";
let dogruHarfler = [];
let hataliTahmin = 0;
const maxHak = 6;

function kategoriSec(kategori) {
  document.getElementById("kategori-secimi").style.display = "none";
  const liste = kelimeListesi[kategori];
  const secim = liste[Math.floor(Math.random() * liste.length)];
  secilenKelime = secim.kelime;
  document.getElementById("oyun-alani").style.display = "block";
  document.getElementById("ipucu").innerText = secim.ipucu;

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
</script>

</body>
</html>
