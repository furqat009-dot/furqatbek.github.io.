<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Video Muharrir Mini App</title>
    <style>
        body { font-family: sans-serif; padding: 20px; }
        h1 { color: #333; }
        button { background-color: #007AFF; color: white; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; }
    </style>
</head>
<body>
    <<body>
    <h1>Video yuklash</h1>
    <p>Tahrirlash uchun video faylni tanlang.</p>
    <input type="file" id="videoInput" accept="video/*">
    <video id="videoPlayer" controls style="width: 100%; margin-top: 10px; display: none;"></video>
    <p id="statusArea" style="color: green; display: none;"></p>
    
    <!-- Telegram Web App API skriptini yuklash -->
    <script src="telegram.org"></script>
    <script>
        // JavaScript kod bu yerga tushadi
    </script>
</body>


    <!-- Telegram Web App API skriptini yuklash -->
    <script src="telegram.org"></script    <script>
        Telegram.WebApp.ready();

        const videoInput = document.getElementById('videoInput');
        const videoPlayer = document.getElementById('videoPlayer');
        const statusArea = document.getElementById('statusArea');

        videoInput.addEventListener('change', function(event) {
            const file = event.target.files[0];
            if (file && file.type.startsWith('video/')) {
                const fileURL = URL.createObjectURL(file);
                videoPlayer.src = fileURL;
                videoPlayer.style.display = 'block';
                statusArea.textContent = `Fayl muvaffaqiyatli yuklandi: ${file.name}`;
                statusArea.style.display = 'block';
                // Bu yerga kelajakda tahrirlash funksiyalari qo'shiladi
            } else {
                statusArea.textContent = 'Noto\'g\'ri fayl turi. Iltimos, video fayl tanlang.';
                statusArea.style.color = 'red';
                statusArea.style.display = 'block';
            }
        });
    </script>

    <script>
        // Bu yerga JavaScript kodlarimizni yozamiz
        Telegram.WebApp.ready();

        // Asosiy tugmani faollashtirish
        Telegram.WebApp.MainButton.setText('Boshlash');
        Telegram.WebApp.MainButton.show();

        // Tugma bosilganda nima qilish kerakligini aniqlash
        Telegram.WebApp.MainButton.onClick(function() {
            Telegram.WebApp.showAlert('Tugma bosildi!');
        });
    </script>
</body>
</html>
