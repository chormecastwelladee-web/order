
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ร้านอาหารเช้า & Room Service</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      background: #f3f4f6;
      font-family: 'Prompt', sans-serif;
    }
    .fade-in {
      animation: fadeIn 0.4s ease-in-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }
  </style>
</head>
<body class="flex items-center justify-center h-screen">

  <!-- Popup -->
  <div id="popup" class="fixed inset-0 bg-black bg-opacity-40 flex items-center justify-center z-50 fade-in">
    <div class="bg-white rounded-2xl shadow-xl w-11/12 max-w-lg flex flex-col md:flex-row items-center md:items-start p-6 space-y-4 md:space-y-0 md:space-x-5">
      
      <!-- โลโก้ -->
      <div class="flex flex-col items-center md:items-start">
        <img src="Logo_Welladee-01.jpg" alt="Welladee Logo" class="w-28 md:w-32 rounded-xl shadow-sm mb-2">
      </div>

      <!-- เนื้อหาข้อความ -->
      <div class="flex-1 text-center md:text-left">
        <h2 class="text-xl font-semibold text-gray-800 mb-2" id="popup-title">แจ้งบริการ</h2>
        <p class="text-gray-600 leading-relaxed" id="popup-message">กำลังตรวจสอบเวลา...</p>
        <div class="flex justify-center md:justify-start">
          <button id="ok-btn"
            class="mt-5 bg-gradient-to-r from-blue-500 to-blue-600 hover:from-blue-600 hover:to-blue-700 text-white font-medium py-2 px-6 rounded-xl transition shadow-md">
            ตกลง
          </button>
        </div>
      </div>
    </div>
  </div>

  <script>
    const popup = document.getElementById("popup");
    const message = document.getElementById("popup-message");
    const okBtn = document.getElementById("ok-btn");

    const now = new Date();
    const hours = now.getHours();

    let canEnter = true; // ถ้าอยากให้ตรวจเวลา ใส่เงื่อนไขได้ทีหลัง
    const nextPageUrl = "img.html";

    // ข้อความที่จะแสดงใน popup
    message.innerHTML = `
      🛎️ <b>Room Service เปิดให้บริการตั้งแต่เวลา 9.00 - 17:30 น.</b>, Room Service is available from 9:00 AM to 5:30 PM.<br><br>
      
      กรุณากด “ตกลง” เพื่อเข้าสู่หน้าเมนูอาหาร 
Please click "OK" to access the menu page.
    `;

    // เมื่อกดปุ่ม "ตกลง"
    okBtn.addEventListener("click", () => {
      if (canEnter) {
        window.location.href = nextPageUrl;
      } else {
        alert("กรุณากลับมาใหม่หลังเวลา 07:00 น.");
      }
    });
  </script>

</body>
</html>

