<!DOCTYPE html>
<html lang="si">
<head>
    <meta charset="UTF-8">
    <title>DansalSnap - කැමරාව</title>
    <style>
        body { font-family: sans-serif; text-align: center; background-color: #f0f0f0; padding: 20px; }
        video { width: 100%; max-width: 400px; border-radius: 20px; background: #000; }
        .btn { padding: 15px 30px; margin: 10px; border-radius: 50px; border: none; background: #ff6600; color: white; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>

    <h2>DansalSnap - පින්තූරයක් ගන්න</h2>
    <video id="video" autoplay playsinline></video>
    <br>
    <button class="btn" onclick="takePhoto()">පින්තූරයක් ගන්න</button>
    <canvas id="canvas" style="display:none;"></canvas>

    <script>
        const video = document.getElementById('video');
        // කැමරාව ක්‍රියාත්මක කිරීම
        navigator.mediaDevices.getUserMedia({ video: true })
            .then(stream => { video.srcObject = stream; })
            .catch(err => { console.error("කැමරාව සොයාගත නොහැක: ", err); });

        function takePhoto() {
            const canvas = document.getElementById('canvas');
            canvas.getContext('2d').drawImage(video, 0, 0, canvas.width, canvas.height);
            alert("පින්තූරය ලබාගන්නා ලදී!");
        }
    </script>
</body>
</html>

