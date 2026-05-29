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

<!DOCTYPE html>
<html lang="si">
<head>
    <meta charset="UTF-8">
    <title>WAX E-commerce</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

    <nav class="flex justify-between items-center p-6 bg-white shadow-md">
        <h1 class="text-2xl font-bold text-blue-600">WAX</h1>
        <div class="space-x-6">
            <a href="#" class="text-gray-700">මුල් පිටුව</a>
            <a href="#" class="text-gray-700">Cart (0)</a>
            <button class="bg-black text-white px-4 py-2 rounded">Login</button>
        </div>
    </nav>

    <div class="p-10 grid grid-cols-1 md:grid-cols-4 gap-6" id="product-container">
        <div class="border p-4 rounded-lg bg-white shadow-lg hover:shadow-2xl transition">
            <img src="https://images.unsplash.com/photo-1596704017254-9b121068fb31?w=500" class="w-full h-48 object-cover rounded">
            <h2 class="mt-4 font-bold text-lg">Ghost Chili</h2>
            <p class="text-gray-500">Rs. 500</p>
            <button onclick="alert('Cart එකට එකතු විය!')" class="mt-4 w-full bg-blue-600 text-white py-2 rounded hover:bg-blue-700">Add to Cart</button>
        </div>
    </div>

    <div class="fixed bottom-10 right-10">
        <button onclick="alert('AI සහායකයා සක්‍රීයයි!')" class="bg-blue-600 text-white p-4 rounded-full shadow-lg">
            AI උදව්
        </button>
    </div>

</body>
</html>
