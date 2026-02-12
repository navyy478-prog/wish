HAPPY VALENTINE DAY ❤️
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Teena ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #ff4d6d;
            --accent: #ffb3c1;
            --glass: rgba(255, 255, 255, 0.2);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }

        body {
            overflow: hidden;
            background: #ffafbd; 
            background: linear-gradient(-45deg, #ffafbd, #ffc3a0, #ff1361, #ff5f6d);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        canvas { position: fixed; top: 0; left: 0; pointer-events: none; z-index: 999; }

        /* Floating Rose Petals */
        .petal {
            position: fixed;
            background-color: #ff4d6d;
            border-radius: 150% 0 150% 0;
            opacity: 0.7;
            pointer-events: none;
            z-index: 1;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg); }
            100% { transform: translateY(110vh) rotate(360deg); }
        }

        .container {
            width: 90%;
            max-width: 420px;
            background: var(--glass);
            backdrop-filter: blur(15px);
            padding: 35px 25px;
            border-radius: 30px;
            border: 1px solid rgba(255, 255, 255, 0.4);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
            z-index: 10;
            display: none;
            color: white;
            text-align: center;
            animation: popIn 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .active { display: block; }

        @keyframes popIn { from { transform: scale(0.5); opacity: 0; } to { transform: scale(1); opacity: 1; } }

        h1 { font-family: 'Dancing Script', cursive; font-size: 2.5rem; margin-bottom: 10px; }
        
        .btn {
            background: white;
            color: var(--primary);
            border: none;
            padding: 14px 32px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .btn:hover { transform: scale(1.05); box-shadow: 0 15px 25px rgba(255,77,109,0.3); }

        .gif-img { width: 150px; border-radius: 20px; margin-bottom: 15px; border: 4px solid white; }

        .box-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; margin: 20px 0; }
        .gift-box { 
            background: white; font-size: 35px; height: 80px; display: flex; align-items: center; 
            justify-content: center; border-radius: 15px; cursor: pointer; transition: 0.3s;
        }
        .gift-box:hover { transform: translateY(-5px) rotate(5deg); }

        #no-btn { transition: 0.3s ease; }

        .letter-box { background: #fff; color: #333; padding: 25px; border-radius: 20px; text-align: left; display: none; }
        .signature { 
            font-family: 'Dancing Script', cursive; font-size: 1.8rem; color: var(--primary); 
            text-align: right; margin-top: 10px; 
        }

        #game-overlay { display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(255,77,109,0.95); z-index:1000; }
    </style>
</head>
<body>

    <canvas id="canvas"></canvas>
    <audio id="bgMusic" loop src="https://www.bensound.com/bensound-music/bensound-love.mp3"></audio>

    <div id="p1" class="container active">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp4Zmt4bXo2d2R4Zmt4bXo2d2R4Zmt4bXo2d2R4Zmt4bXo2dyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/KzM1lAfJjCW3Ic7vql/giphy.gif" class="gif-img">
        <h1>Happy Valentine's Day Teena ❤️</h1>
        <p>I built this little digital world for you. Want to see the magic?</p>
        <button class="btn" onclick="next(2)">Start Journey ✨</button>
    </div>

    <div id="p2" class="container">
        <h1>For My Soulmate</h1>
        <p style="font-style: italic; font-size: 1.3rem; margin: 15px 0;">
            "Aankhon ki chamak, chehre ka noor,<br>
            Aapko dekh kar dil hota hai choor choor.<br>
            Khuda se bas yahi maangi hai dua,<br>
            Aap humse kabhi na hona door."
        </p>
        <p>— <b>Navuddin</b></p>
        <button class="btn" onclick="next(3)">Continue to Fun 🎁</button>
    </div>

    <div id="p3" class="container">
        <h1>Unlock Your Hearts 🎁</h1>
        <p>Tap a box and catch 5 hearts to reveal a message!</p>
        <div class="box-grid">
            <div class="gift-box" onclick="startGame(0)">🎁</div>
            <div class="gift-box" onclick="startGame(1)">🎁</div>
            <div class="gift-box" onclick="startGame(2)">🎁</div>
        </div>
        <div id="game-msg" style="background: rgba(255,255,255,0.2); padding: 10px; border-radius: 10px; min-height: 40px;"></div>
        <button class="btn" onclick="next(4)">Ask Me Something 💍</button>
    </div>

    <div id="p4" class="container">
        <h1>Will You Be My Valentine? 💍</h1>
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp4Zmt4bXo2d2R4Zmt4bXo2d2R4Zmt4bXo2d2R4Zmt4bXo2dyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/c76IJLufpNwSULPk2m/giphy.gif" class="gif-img">
        <div>
            <button class="btn" onclick="celebrate()">YES! 😍</button>
            <button id="no-btn" class="btn" onmouseover="moveNo()" style="background: #444; color: white;">No</button>
        </div>
        <p id="tease" style="margin-top: 15px; color: yellow; font-weight: bold;"></p>
    </div>

    <div id="p5" class="container">
        <h1>Secret Love Letter 🔐</h1>
        <div id="lock">
            <p style="margin-bottom: 10px;">To read the letter, enter your name:</p>
            <button class="btn" onclick="unlock()">Unlock 🔓</button>
        </div>
        <div id="letter" class="letter-box">
            <p>My Dearest Teena,</p>
            <p>Every single day with you feels like a blessing. You are my best friend and my heart's peace. I promise to hold your hand forever.</p>
            <h2 style="color: #ff1361; text-align: center; margin: 15px 0;">I LOVE YOU FOREVER ❤️</h2>
            <div class="signature">Ur Navuu</div>
        </div>
    </div>

    <div id="game-overlay">
        <h2 style="margin-top: 20%; color:white;">Catch 5 Hearts! <span id="score">0</span>/5</h2>
    </div>

    <script>
        // Rose Petals Falling
        function createPetals() {
            const petal = document.createElement('div');
            petal.classList.add('petal');
            petal.style.left = Math.random() * 100 + 'vw';
            petal.style.width = Math.random() * 15 + 10 + 'px';
            petal.style.height = petal.style.width;
            petal.style.animationDuration = Math.random() * 3 + 4 + 's';
            document.body.appendChild(petal);
            setTimeout(() => petal.remove(), 7000);
        }
        setInterval(createPetals, 300);

        function next(n) {
            document.querySelectorAll('.container').forEach(c => c.classList.remove('active'));
            document.getElementById('p' + n).classList.add('active');
            document.getElementById('bgMusic').play().catch(()=>{});
        }

        function moveNo() {
            const btn = document.getElementById('no-btn');
            document.getElementById('tease').innerText = "No button nahi dabni chahiye! 😜";
            btn.style.position = 'fixed';
            btn.style.left = Math.random() * 70 + 15 + 'vw';
            btn.style.top = Math.random() * 70 + 15 + 'vh';
        }

        let score = 0;
        const boxMsgs = ["Teena, you are my world! 🌎", "Your smile is my favorite! 😊", "Forever Yours! 💖"];
        function startGame(idx) {
            score = 0; document.getElementById('score').innerText = score;
            document.getElementById('game-overlay').style.display = 'block';
            spawnHeart(idx);
        }

        function spawnHeart(idx) {
            if(score >= 5) {
                document.getElementById('game-overlay').style.display = 'none';
                document.getElementById('game-msg').innerText = boxMsgs[idx];
                return;
            }
            const h = document.createElement('div');
            h.innerHTML = '❤️';
            h.style.position = 'absolute';
            h.style.fontSize = '50px';
            h.style.left = Math.random() * 80 + 10 + '%';
            h.style.top = Math.random() * 80 + 10 + '%';
            h.style.cursor = 'pointer';
            h.onclick = () => { score++; document.getElementById('score').innerText = score; h.remove(); spawnHeart(idx); };
            document.getElementById('game-overlay').appendChild(h);
        }

        function celebrate() {
            startFireworks();
            setTimeout(() => next(5), 2000);
        }

        function unlock() {
            let pass = prompt("Enter Password (Hint: Your Name):");
            if(pass && pass.toLowerCase() === 'teena') {
                document.getElementById('lock').style.display = 'none';
                document.getElementById('letter').style.display = 'block';
                startFireworks();
            } else { alert("Try again, My Love!"); }
        }

        // Firecrackers Logic
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth; canvas.height = window.innerHeight;
        let particles = [];
        function startFireworks() {
            for(let i=0; i<150; i++) {
                particles.push({
                    x: canvas.width / 2, y: canvas.height / 2,
                    sx: Math.random() * 8 - 4, sy: Math.random() * 8 - 4,
                    size: Math.random() * 3 + 1, color: `hsl(${Math.random() * 360}, 100%, 60%)`
                });
            }
            animate();
        }
        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach((p, i) => {
                p.x += p.sx; p.y += p.sy; p.sy += 0.1;
                ctx.fillStyle = p.color;
                ctx.beginPath(); ctx.arc(p.x, p.y, p.size, 0, Math.PI * 2); ctx.fill();
                if(p.y > canvas.height) particles.splice(i, 1);
            });
            if(particles.length > 0) requestAnimationFrame(animate);
        }
    </script>
</body>
</html>
