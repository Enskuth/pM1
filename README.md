<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>สถานะคุณภาพอากาศธรรมชาติ</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Sarabun:wght@400;700&display=swap');

    :root {
      --bg1: #c8e6c9;
      --bg2: #a5d6a7;
      --bg3: #b3e5fc;
      --bg4: #f0f4c3;
    }

    body {
      font-family: 'Sarabun', sans-serif;
      margin: 0;
      animation: bgFade 20s infinite alternate;
      background-size: 400% 400%;
      overflow-x: hidden;
    }

    @keyframes bgFade {
      0%   { background: var(--bg1); }
      25%  { background: var(--bg2); }
      50%  { background: var(--bg3); }
      75%  { background: var(--bg4); }
      100% { background: var(--bg1); }
    }

    header {
      background: linear-gradient(to right, #81c784, #66bb6a);
      color: white;
      padding: 30px;
      text-align: center;
      font-size: 26px;
      font-weight: bold;
      position: relative;
      z-index: 2;
    }

    .container {
      max-width: 900px;
      margin: 30px auto;
      padding: 20px;
      z-index: 2;
      position: relative;
    }

    h2 {
      font-size: 22px;
      color: #2e7d32;
      border-bottom: 2px solid #a5d6a7;
      padding-bottom: 5px;
    }

    .filter-status {
      background-color: #e8f5e9;
      border-left: 8px solid #388e3c;
      padding: 20px;
      border-radius: 12px;
      margin-bottom: 30px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .progress-bar {
      background-color: #c8e6c9;
      border-radius: 20px;
      overflow: hidden;
      height: 22px;
      margin-top: 10px;
    }

    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, #66bb6a, #388e3c);
      color: white;
      font-size: 14px;
      text-align: center;
      line-height: 22px;
      width: 87%;
      animation: growBar 2s ease-out;
    }

    @keyframes growBar {
      from { width: 0; }
      to { width: 87%; }
    }

    .aqi-level {
      border-radius: 12px;
      padding: 15px 20px;
      margin: 15px 0;
      color: white;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      transition: transform 0.3s;
    }

    .aqi-level:hover {
      transform: scale(1.03);
    }

    .blue { background-color: #4fc3f7; }
    .green { background-color: #66bb6a; }
    .yellow { background-color: #fbc02d; color: #000; }
    .orange { background-color: #f57c00; }
    .red { background-color: #d32f2f; }

    footer {
      text-align: center;
      padding: 20px;
      font-size: 14px;
      color: #555;
      background-color: #e0f2f1;
      z-index: 2;
      position: relative;
    }

    /* ใบไม้ตก */
    .leaf {
      position: fixed;
      top: -100px;
      width: 40px;
      height: 40px;
      pointer-events: none;
      z-index: 1;
      animation: fall 10s linear infinite;
    }

    @keyframes fall {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(120vh) rotate(360deg);
        opacity: 0;
      }
    }

  </style>
</head>
<body>

<header>
  สถานะคุณภาพอากาศ & ระบบกรองอากาศ
</header>

<!-- ใบไม้หลายใบ -->
<img src="https://cdn-icons-png.flaticon.com/512/766/766894.png" class="leaf" style="left: 5%; animation-delay: 0s;">
<img src="https://cdn-icons-png.flaticon.com/512/766/766894.png" class="leaf" style="left: 20%; animation-delay: 2s;">
<img src="https://cdn-icons-png.flaticon.com/512/766/766894.png" class="leaf" style="left: 35%; animation-delay: 4s;">
<img src="https://cdn-icons-png.flaticon.com/512/766/766894.png" class="leaf" style="left: 50%; animation-delay: 1s;">
<img src="https://cdn-icons-png.flaticon.com/512/766/766894.png" class="leaf" style="left: 70%; animation-delay: 3s;">
<img src="https://cdn-icons-png.flaticon.com/512/766/766894.png" class="leaf" style="left: 85%; animation-delay: 5s;">

<div class="container">

  <h2>🌿 สถานะการกรองอากาศ</h2>
  <div class="filter-status">
    <p>🔵 <strong>ค่าฝุ่นก่อนกรอง:</strong> 185 µg/m³</p>
    <p>🟢 <strong>ค่าฝุ่นหลังกรอง:</strong> 24 µg/m³</p>
    <p>✅ <strong>ประสิทธิภาพการกรอง:</strong></p>
    <div class="progress-bar">
      <div class="progress-fill">87%</div>
    </div>
    <p>อากาศภายในอยู่ในระดับดีมาก เหมาะกับการพักผ่อน 🌱</p>
  </div>

  <h2>🌤 ระดับค่าฝุ่น PM 2.5</h2>

  <div class="aqi-level blue">
    <strong>0-25:</strong> คุณภาพอากาศดีมาก — เหมาะกับกิจกรรมกลางแจ้งและท่องเที่ยว
  </div>

  <div class="aqi-level green">
    <strong>26-50:</strong> คุณภาพอากาศดี — ทำกิจกรรมกลางแจ้งได้ตามปกติ
  </div>

  <div class="aqi-level yellow">
    <strong>51-100:</strong> ปานกลาง — กลุ่มเสี่ยงควรระวังหากมีอาการผิดปกติ
  </div>

  <div class="aqi-level orange">
    <strong>101-200:</strong> เริ่มมีผลต่อสุขภาพ — ควรลดกิจกรรมนอกบ้าน
  </div>

  <div class="aqi-level red">
    <strong>201 ขึ้นไป:</strong> มีผลกระทบต่อสุขภาพ — หลีกเลี่ยงกิจกรรมกลางแจ้งและสวมหน้ากาก
  </div>

</div>

<footer>
  🌿 ข้อมูลเพื่อการศึกษา | ตกแต่งในธีมธรรมชาติพร้อมภาพเคลื่อนไหว
</footer>

</body>
</html>
