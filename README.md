<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Harun Tır Parası</title>
  <style>
    body {
      text-align: center;
      font-family: Arial, sans-serif;
      background: #f0f0f0;
    }
    #money {
      font-size: 2em;
      margin: 20px;
    }
    #clickImage {
      width: 250px;
      cursor: pointer;
      border-radius: 10px;
    }
    .shop {
      margin-top: 30px;
    }
    .item {
      display: inline-block;
      margin: 20px;
      text-align: center;
    }
    .item img {
      width: 100px;
      cursor: pointer;
      border: 2px solid #ccc;
      border-radius: 10px;
    }
    .item p {
      margin: 10px 0;
    }
  </style>
</head>
<body>
  <h1>Harun Tır Parası</h1>
  <div id="money">TL: 0</div>
  
  <!-- Ana tıklama resmi -->
  <img id="clickImage" src="https://media.licdn.com/dms/image/v2/D4D03AQEA19AYbyBbpg/profile-displayphoto-shrink_200_200/profile-displayphoto-shrink_200_200/0/1719032428100?e=2147483647&v=beta&t=uyQjFwQL6iJpFJRyypeoqQ2yWPVvRFDweWQchhsVgNE" alt="Clicker Resmi">

  <!-- Mağaza -->
  <div class="shop">
    <h2>Mağaza</h2>
    <div class="item" id="item1">
      <img src="https://e7.pngegg.com/pngimages/977/479/png-clipart-wheelbarrow-architectural-engineering-scaffolding-manufacturing-wheelbarrow-miscellaneous-quality.png" alt="Item 1">
      <p>Fiyat: 10 TL</p>
      <p>+2 TL / tıklama</p>
    </div>
    <div class="item" id="item2">
      <img src="https://cdn.wannart.com/production/post/2019/12/20258076.jpg-r_1920_1080-f_jpg-q_x-xxyxx.jpg" alt="Item 2">
      <p>Fiyat: 50 TL</p>
      <p>+5 TL / tıklama</p>
    </div>
    <div class="item" id="item3">
      <img src="https://stcorpwebblobprod.blob.core.windows.net/tcorpblob/truckstore01banner2021-04-0320210403t183427252_2021-04-1920210419T113654005.jpg" alt="Item 3">
      <p>Fiyat: 200 TL</p>
      <p>+20 TL / tıklama</p>
    </div>
  </div>

  <script>
    let money = 0;
    let perClick = 1; // başlangıçta her tıklama 1 TL
    const moneyDisplay = document.getElementById("money");
    const image = document.getElementById("clickImage");

    // Tıklama ile para kazanma
    image.addEventListener("click", () => {
      money += perClick;
      moneyDisplay.textContent = "TL: " + money;
    });

    // Item 1
    document.getElementById("item1").addEventListener("click", () => {
      if (money >= 10) {
        money -= 10;
        perClick = 2;
        moneyDisplay.textContent = "TL: " + money;
        alert("Item 1 alındı! Artık her tıklama 2 TL kazandırıyor.");
      } else {
        alert("Yeterli paran yok!");
      }
    });

    // Item 2
    document.getElementById("item2").addEventListener("click", () => {
      if (money >= 50) {
        money -= 50;
        perClick = 5;
        moneyDisplay.textContent = "TL: " + money;
        alert("Item 2 alındı! Artık her tıklama 5 TL kazandırıyor.");
      } else {
        alert("Yeterli paran yok!");
      }
    });

    // Item 3
    document.getElementById("item3").addEventListener("click", () => {
      if (money >= 200) {
        money -= 200;
        perClick = 20;
        moneyDisplay.textContent = "TL: " + money;
        alert("Item 3 alındı! Artık her tıklama 20 TL kazandırıyor.");
      } else {
        alert("Yeterli paran yok!");
      }
    });
  </script>
</body>
</html>
