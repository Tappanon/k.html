# k.html
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>ค้นหาแคลอรี่อาหาร</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      max-width: 600px;
      margin: auto;
      padding: 20px;
    }
    input {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      margin-bottom: 20px;
    }
    .result {
      font-size: 18px;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <h1>🔍 ค้นหาแคลอรี่อาหาร</h1>
  <input type="text" id="searchInput" placeholder="พิมพ์ชื่อเมนูอาหาร...">
  <div class="result" id="resultBox"></div>

  <script>
    // ฐานข้อมูลเมนูอาหาร 50 รายการ (ตัวอย่าง)
    const foodData = {
      "ข้าวผัดหมู": 520,
      "ข้าวมันไก่": 596,
      "ข้าวไข่เจียว": 445,
      "ผัดไทยกุ้งสด": 540,
      "ข้าวกะเพราไก่ไข่ดาว": 630,
      "ข้าวขาหมู": 690,
      "ราดหน้าเส้นใหญ่หมู": 400,
      "ส้มตำไทย": 120,
      "แกงเขียวหวานไก่": 280,
      "แกงส้มผักรวม": 95,
      "ต้มยำกุ้ง": 120,
      "ขนมจีนน้ำยา": 332,
      "ผัดซีอิ๊วหมู": 480,
      "ข้าวหมูแดง": 541,
      "ข้าวหน้าเป็ด": 495,
      "ก๋วยเตี๋ยวเรือ": 200,
      "ก๋วยเตี๋ยวต้มยำ": 320,
      "ข้าวเหนียวหมูปิ้ง": 440,
      "ข้าวหมูกระเทียม": 480,
      "ข้าวผัดกะเพราเนื้อ": 600,
      "ยำวุ้นเส้น": 150,
      "ข้าวผัดกุ้ง": 540,
      "ข้าวหมูทอดกระเทียม": 500,
      "ผัดคะน้าหมูกรอบ": 520,
      "ข้าวคลุกกะปิ": 450,
      "ข้าวแกงเผ็ดเป็ดย่าง": 530,
      "สุกี้น้ำไก่": 280,
      "ข้าวต้มปลา": 150,
      "ข้าวผัดปู": 510,
      "ขนมจีบ": 200,
      "ซาลาเปาไส้หมูสับ": 250,
      "ไก่ทอด": 300,
      "ขนมปังหน้าหมู": 320,
      "ลาบหมู": 200,
      "น้ำตกหมู": 180,
      "ข้าวหมูย่าง": 550,
      "ก๋วยจั๊บ": 350,
      "โจ๊กหมูไข่ลวก": 250,
      "บะหมี่เกี๊ยวหมูแดง": 450,
      "ผัดผักรวมมิตร": 220,
      "แกงจืดเต้าหู้หมูสับ": 90,
      "ข้าวหน้าไก่เทอริยากิ": 510,
      "ไข่ต้ม": 75,
      "ไข่ดาว": 90,
      "ข้าวไข่ข้น": 420,
      "ไข่เจียวหมูสับ": 400,
      "ไข่ลูกเขย": 270,
      "ทอดมันปลา": 240,
      "แกงพะแนง": 350,
      "หมูปิ้งไม้ละ": 90
    };

    const searchInput = document.getElementById("searchInput");
    const resultBox = document.getElementById("resultBox");

    searchInput.addEventListener("input", function () {
      const keyword = this.value.trim();
      if (keyword === "") {
        resultBox.innerHTML = "";
        return;
      }

      let found = false;
      for (const [food, calories] of Object.entries(foodData)) {
        if (food.includes(keyword)) {
          resultBox.innerHTML = `<strong>${food}</strong>: ${calories} กิโลแคลอรี่`;
          found = true;
          break;
        }
      }

      if (!found) {
        resultBox.innerHTML = `ไม่พบเมนู "${keyword}"`;
      }
    });
  </script>
</body>
</html>
