<video id="videoPlayer" controls style="width: 100%; margin-top: 10px; display: none;"></video>

<!-- Yangi tahrirlash tugmasi -->
<button id="editButton" style="display: none; margin-top: 10px;">Tahrirlashni boshlash</button>

<p id="statusArea" style="color: green; display: none;"></p>
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Video Muharrir Mini App</title>
    <style>
        body { font-family: sans-serif; padding: 20px; }
        h1 { color: #333; }
        input[type="file"] { margin-bottom: 10px; }
        video { border: 1px solid #ccc; }
    </style>
</head>
<body>
    <h1>Video yuklash</h1>
    <p>Tahrirlash uchun video faylni tanlang.</p>
    <input type="file" id="videoInput" accept="video/*">
    <video id="videoPlayer" controls style="width: 100%; margin-top: 10px; display: none;"></video>
    <p id="statusArea" style="color: green; display: none;"></p>
    
    <!-- Telegram Web App API skriptini yuklash -->
    <script src="telegram.org"></script>
    <script>
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
            } else {
                statusArea.textContent = 'Noto\'g\'ri fayl turi. Iltimos, video fayl tanlang.';
                statusArea.style.color = 'red';
                statusArea.style.display = 'block';
            }
        });
    </script>
</body>
</html>
