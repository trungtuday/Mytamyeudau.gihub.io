# Mytamyeudau.gihub.io
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sunflower Love</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      overflow: hidden;
      height: 100%;
      font-family: 'Segoe UI', sans-serif;
      background: black;
    }

    video#bgVideo {
      position: fixed;
      top: 50%;
      left: 50%;
      min-width: 100%;
      min-height: 100%;
      transform: translate(-50%, -50%);
      object-fit: cover;
      z-index: -1;
      filter: brightness(0.9);
      animation: slowZoom 60s infinite alternate ease-in-out;
    }

    @keyframes slowZoom {
      from { transform: translate(-50%, -50%) scale(1); }
      to   { transform: translate(-50%, -50%) scale(1.05); }
    }

    .message {
      position: absolute;
      white-space: nowrap;
      font-size: 4vw;
      animation: moveLeft 20s linear infinite;
      font-weight: bold;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.6);
    }

    @keyframes moveLeft {
      0% { left: 100vw; }
      100% { left: -100vw; }
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>
  <video id="bgVideo" autoplay muted loop playsinline>
    <source src="pexels-media-2975799.mp4" type="video/mp4">
  </video>
  <audio autoplay loop>
    <source src="Anh-Nang-Cua-Anh.mp3" type="audio/mpeg">
  </audio>

  <script>
    const messages = [
      "🥰 Gửi em, bông hoa đẹp nhất giữa cánh đồng mặt trời 🥰",
      "💖 Anh yêu nụ cười của em 💖",
      "🌼 Ở bên em, mọi thứ đều trở nên tuyệt vời 🌼",
      "💫 Em là ánh nắng làm bừng sáng tim anh 💫",
      "💝 Anh cảm ơn vì em luôn ở đây 💝",
      "🌟 Dù thế giới có ra sao, em vẫn là điều tuyệt vời nhất 🌟",
      "💗 Em là lý do khiến mỗi ngày của anh ý nghĩa 💗",
      "🥰 Yêu em là điều đẹp nhất cuộc đời anh 🥰",
      "🌈 Chỉ cần là em, anh có thể vượt qua mọi khó khăn 🌈",
      "💞 Anh muốn cùng em đi đến hết cuộc đời 💞"
    ];

    const colors = ["#ff69b4", "#ffffff", "#dda0dd", "#ffff66"]; // hồng, trắng, tím, vàng

    function createMessage(text) {
      const msg = document.createElement("div");
      msg.className = "message";
      msg.innerText = text;
      msg.style.top = Math.random() * 80 + "vh";
      msg.style.color = colors[Math.floor(Math.random() * colors.length)];
      document.body.appendChild(msg);

      setTimeout(() => msg.remove(), 21000);
    }

    setInterval(() => {
      const msg = messages[Math.floor(Math.random() * messages.length)];
      createMessage(msg);
    }, 2000);

    window.onload = () => {
      messages.forEach((msg, i) => {
        setTimeout(() => createMessage(msg), i * 2000);
      });
    };
  </script>
</body>
</html>