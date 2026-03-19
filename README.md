<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Bholu</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { background-color: #ffe4e6; overflow: hidden; display: flex; align-items: center; justify-content: center; height: 100vh; font-family: 'Arial', sans-serif; }
        .container { text-align: center; background: white; padding: 2rem; border-radius: 20px; box-shadow: 0 10px 25px rgba(0,0,0,0.1); width: 90%; max-width: 400px; z-index: 10; }
        #noButton { position: absolute; transition: 0.3s; }
        .bubu-dudu { width: 150px; margin: 0 auto 1rem; }
        .heart { position: absolute; color: #fb7185; font-size: 20px; animation: float 3s linear infinite; top: -10%; }
        @keyframes float { to { transform: translateY(110vh) rotate(360deg); } }
    </style>
</head>
<body>

    <div class="container">
        <img src="https://media.tenor.com/9C3B-G1-fbgAAAAM/bubu-dudu-bubu.gif" alt="Bubu Dudu" class="bubu-dudu">
        <h1 class="text-2xl font-bold text-rose-500 mb-6">Will you be mine forever? ❤️</h1>
        <div class="flex justify-around items-center h-12">
            <button onclick="celebrate()" class="bg-green-500 text-white px-8 py-2 rounded-full font-bold transform hover:scale-110">Yes!</button>
            <button id="noButton" onmouseover="moveButton()" class="bg-rose-500 text-white px-8 py-2 rounded-full font-bold">No</button>
        </div>
    </div>

    <script>
        function moveButton() {
            const btn = document.getElementById('noButton');
            const x = Math.random() * (window.innerWidth - btn.offsetWidth);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight);
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        function celebrate() {
            document.querySelector('.container').innerHTML = `
                <img src="https://media.tenor.com/6Xp9n8_6J30AAAAM/bubu-dudu-panda-bear.gif" class="bubu-dudu">
                <h1 class="text-3xl font-bold text-rose-600 mt-4">Yay! I love you! ❤️</h1>
                <p class="text-gray-500 mt-2">See you soon, Bholu!</p>
            `;
            for(let i=0; i<50; i++) createHeart();
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
            document.body.appendChild(heart);
        }
    </script>
</body>
</html> 
