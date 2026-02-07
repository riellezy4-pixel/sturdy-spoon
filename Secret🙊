<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Little Surprise... ✨</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Montserrat:wght@300;400&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #ff85a1;
            --secondary: #fce4ec;
            --accent: #ff477e;
        }

        body {
            margin: 0;
            padding: 0;
            font-family: 'Montserrat', sans-serif;
            background-color: var(--secondary);
            color: #444;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Lockscreen */
        #lock {
            position: fixed;
            inset: 0;
            background: white;
            z-index: 100;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: 0.5s;
        }

        .input-group {
            margin-top: 20px;
        }

        input {
            padding: 12px;
            border: 2px solid var(--primary);
            border-radius: 25px;
            outline: none;
            text-align: center;
        }

        /* Main Container */
        .container {
            text-align: center;
            padding: 20px;
            max-width: 400px;
            width: 100%;
        }

        .polaroid {
            background: white;
            padding: 15px 15px 40px 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transform: rotate(-3deg);
            margin-bottom: 30px;
            transition: 0.3s;
        }

        .polaroid:hover {
            transform: rotate(0deg) scale(1.05);
        }

        .polaroid img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border: 1px solid #eee;
        }

        h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 2.5rem;
            color: var(--accent);
            margin-bottom: 30px;
        }

        .btn-group {
            display: flex;
            justify-content: center;
            gap: 15px;
            align-items: center;
            flex-wrap: wrap;
        }

        button {
            padding: 12px 25px;
            border-radius: 30px;
            border: none;
            cursor: pointer;
            font-weight: bold;
            transition: 0.2s;
        }

        #yesBtn {
            background-color: var(--accent);
            color: white;
            font-size: 1.2rem;
        }

        #noBtn {
            background-color: #ddd;
            color: #666;
        }

        /* Success State */
        #success {
            display: none;
            animation: fadeIn 1s;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .message-box {
            font-family: 'Dancing Script', cursive;
            font-size: 1.5rem;
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            margin-top: 20px;
        }

        .floating-heart {
            position: fixed;
            color: var(--primary);
            pointer-events: none;
            z-index: -1;
            animation: float 4s linear infinite;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <div id="lock">
        <h1>For Your Eyes Only ✨</h1>
        <div class="input-group">
            <input type="password" id="passwordInput" placeholder="Password?">
            <button onclick="checkPass()" style="background: var(--primary); color: white;">Open 💌</button>
        </div>
        <p style="font-size: 0.8rem; margin-top: 10px;">Hint: "mylove"</p>
    </div>

    <div class="container" id="mainContent">
        <div id="proposal">
            <div class="polaroid">
                <img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=500" alt="Us">
            </div>
            <h1>Will you be my Valentine? 🌹</h1>
            <div class="btn-group">
                <button id="yesBtn" onclick="celebrate()">YES!</button>
                <button id="noBtn" onmouseover="moveNo()">No</button>
            </div>
        </div>

        <div id="success">
            <div class="polaroid">
                <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHYxc2x4Y2x4Z3R4Z3R4Z3R4Z3R4Z3R4Z3R4Z3R4Z3R4Z3R4Z3R4Z3R4Z3ImZXA9djFfaW50ZXJuYWxfZ2lmX2J5X2lkJmN0PWc/c76IJLufpNwSULPk77/giphy.gif" alt="Happy">
            </div>
            <h1>Yay! I love you! ❤️</h1>
            <div class="message-box">
                "You make every day feel like a dream. I can't wait to spend this Valentine's Day with you."
            </div>
        </div>
    </div>

    <script>
        function checkPass() {
            const pass = document.getElementById('passwordInput').value;
            if(pass.toLowerCase() === "mylove") {
                document.getElementById('lock').style.opacity = "0";
                setTimeout(() => {
                    document.getElementById('lock').style.display = "none";
                }, 500);
            } else {
                alert("Try again, beautiful!");
            }
        }

        let yesSize = 1.2;
        function moveNo() {
            const noBtn = document.getElementById('noBtn');
            const yesBtn = document.getElementById('yesBtn');
            
            // Randomly move No button
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.position = "absolute";
            noBtn.style.left = x + "px";
            noBtn.style.top = y + "px";

            // Make Yes button grow
            yesSize += 0.3;
            yesBtn.style.transform = `scale(${yesSize})`;
        }

        function celebrate() {
            document.getElementById('proposal').style.display = "none";
            document.getElementById('success').style.display = "block";
            
            // Create hearts
            for(let i=0; i<50; i++) {
                setTimeout(createHeart, i * 100);
            }
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('floating-heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.fontSize = (Math.random() * 20 + 10) + "px";
            heart.style.duration = (Math.random() * 3 + 2) + "s";
            document.body.appendChild(heart);
            
            setTimeout(() => { heart.remove(); }, 4000);
        }
    </script>
</body>
</html>

