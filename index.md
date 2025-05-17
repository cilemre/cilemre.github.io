<!-- tüm stil kodları aynı kalacak, sadece aşağıya yeni stil ve html+js kodu eklenecek -->
<style>
  #adamCizimi {
    width: 200px;
    height: 250px;
    margin: 20px auto;
    position: relative;
  }

  .parca {
    position: absolute;
    background-color: #eee;
  }

  .kule { width: 10px; height: 200px; left: 0; bottom: 0; }
  .ust { width: 100px; height: 10px; left: 0; top: 0; }
  .ip { width: 2px; height: 30px; left: 98px; top: 10px; }
  .kafa { width: 30px; height: 30px; border-radius: 50%; left: 83px; top: 40px; background-color: #fff; }
  .govde { width: 2px; height: 50px; left: 98px; top: 70px; }
  .kol1 { width: 2px; height: 30px; left: 98px; top: 80px; transform: rotate(-45deg); transform-origin: top; }
  .kol2 { width: 2px; height: 30px; left: 98px; top: 80px; transform: rotate(45deg); transform-origin: top; }
  .bacak1 { width: 2px; height: 30px; left: 98px; top: 120px; transform: rotate(-30deg); transform-origin: top; }
  .bacak2 { width: 2px; height: 30px; left: 98px; top: 120px; transform: rotate(30deg); transform-origin: top; }
</style>

<!-- adam asmaca bölümü içine adam çizimi divi eklenecek -->
<div id="adamCizimi"></div>

<script>
  const parcalar = [
    "<div class='parca kule'></div>",
    "<div class='parca ust'></div>",
    "<div class='parca ip'></div>",
    "<div class='parca kafa'></div>",
    "<div class='parca govde'></div>",
    "<div class='parca kol1'></div>",
    "<div class='parca kol2'></div>",
    "<div class='parca bacak1'></div>",
    "<div class='parca bacak2'></div>"
  ];

  function adamGuncelle() {
    const adam = document.getElementById("adamCizimi");
    adam.innerHTML = "";
    for (let i = 0; i <= hataliTahmin && i < parcalar.length; i++) {
      adam.innerHTML += parcalar[i];
    }
  }
</script>

<!-- mevcut fonksiyonlara çağrı eklenir -->
<script>
  function oyunBaslat() {
    secilen = kelimeler[Math.floor(Math.random() * kelimeler.length)];
    dogruHarfler = [];
    hataliTahmin = 0;
    document.getElementById("status").innerText = "";
    harfleriOlustur();
    guncelleEkran();
    adamGuncelle();
  }

  function harfTahmin(harf, btn) {
    if (btn) btn.disabled = true;
    if (secilen.includes(harf)) {
      dogruHarfler.push(harf);
    } else {
      hataliTahmin++;
      if (btn) btn.classList.add("wrong");
    }
    guncelleEkran();
    adamGuncelle();
  }
</script>
