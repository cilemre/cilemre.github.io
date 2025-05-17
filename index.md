<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kişisel Sayfa</title>
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

      <div class="oyun-alani" id="kategori-secimi" style="display: none; text-align: center;">
        <h2>Bir Kategori Seç</h2>
        <button class="btn" onclick="kategoriyiBaslat('film')">🎬 Film</button>
        <button class="btn" onclick="kategoriyiBaslat('muhendislik')">⚙️ Mühendislik</button>
      </div>

      <!-- Adam Asmaca alanı -->
      <div class="oyun-alani" id="oyun-alani">
        <h2 id="oyun-baslik">Adam Asmaca</h2>
        <p><strong>Kalan Hak:</strong> <span id="hakSayisi"></span></p>
        <div id="wordDisplay" class="hangman-word"></div>
        <div id="letters"></div>
        <p id="status"></p>
        <div id="svg-hangman-container" style="text-align: center; margin-top: 20px;">
          <!-- SVG kodları burada olacak -->
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

  <!-- KATEGORİLİ ADAM ASMACA SCRIPTİ BURADA -->
  <script>
  // JavaScript kodları: kelime listesi, oyun başlatma, harf tahmin, vs...
  </script>
</body>
</html>
