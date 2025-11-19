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
