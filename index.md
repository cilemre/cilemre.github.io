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
  }

  .oyunlar-sag a:hover {
    text-decoration: underline;
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

    <hr>
    <p style="text-align: center; margin-top: 40px; font-size: 14px; color: #999;">
      İletişim için: <strong>emre.cil@gazi.edu.tr</strong>
    </p>
  </div>

  <aside class="oyunlar-sag">
    <h3>🎮 Oyunlar</h3>
    <ul>
      <li><a href="#">Adam Asmaca</a></li>
      <li><a href="#">Kelime Bulmaca</a></li>
      <li><a href="#">Yeni Oyun</a></li>
    </ul>
  </aside>
</div>
