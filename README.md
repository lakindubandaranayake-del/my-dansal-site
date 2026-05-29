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
<!DOCTYPE html>
<html lang="si">
<head>
    <meta charset="UTF-8">
    <title>DansalSnap AI</title>
    <style>
        body { font-family: sans-serif; background-color: #f9f9f9; padding: 20px; }
        .chat-box { width: 100%; max-width: 400px; height: 300px; border: 1px solid #ccc; background: white; margin: 20px auto; padding: 10px; overflow-y: scroll; border-radius: 15px; }
        .input-area { text-align: center; }
        input { padding: 10px; width: 70%; border-radius: 20px; border: 1px solid #ccc; }
    </style>
</head>
<body>

    <h2>DansalSnap AI සමඟ කතා කරන්න</h2>
    
    <div class="chat-box" id="chatBox">
        <p><b>AI:</b> ආයුබෝවන්! මට දන්සැල් ගැන මොනවාද දැනගන්න ඕනේ?</p>
    </div>

    <div class="input-area">
        <input type="text" id="userInput" placeholder="ඔබේ ප්‍රශ්නය මෙතැන ලියන්න...">
        <button onclick="getAIResponse()">යවන්න</button>
    </div>

    <script>
        function getAIResponse() {
            let userText = document.getElementById("userInput").value;
            let chatBox = document.getElementById("chatBox");
            
            // පරිශීලකයාගේ පණිවිඩය එකතු කිරීම
            chatBox.innerHTML += `<p><b>ඔබ:</b> ${userText}</p>`;
            
            // සරල AI ප්‍රතිචාරයක් (මෙතැනදී ඔබට සැබෑ AI API එකක් සම්බන්ධ කළ හැක)
            setTimeout(() => {
                chatBox.innerHTML += `<p><b>AI:</b> මම තවමත් ඉගෙන ගනිමින් සිටිනවා! ${userText} ගැන මම පසුව ඔබට තොරතුරු දෙන්නම්.</p>`;
                chatBox.scrollTop = chatBox.scrollHeight;
            }, 1000);
            
            document.getElementById("userInput").value = "";
        }
    </script>
</body>
</html>

