<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HBD ALIZA ✨</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@400;500;600;700&display=swap');

        * {
            box-sizing: border-box;
        }
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #fff5f6 0%, #ffe3e7 50%, #ffd6db 100%);
            font-family: 'Poppins', Arial, sans-serif;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        #container {
            position: relative;
            width: 100%;
            max-width: 1300px;
            height: 100%;
            max-height: 850px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
        }
        #text-panel {
            width: 48%;
            z-index: 10;
            display: flex;
            flex-direction: column;
            justify-content: center;
            height: 100%;
            padding-left: 20px;
        }
        .typewriter-text {
            font-size: 1.8rem;
            line-height: 1.4;
            color: #bd2c42;
            font-weight: 600;
            margin-bottom: 15px;
        }
        .highlight-name {
            font-family: 'Dancing Script', cursive;
            font-size: 3.8rem;
            color: #d61c3c;
            font-weight: 700;
            display: inline-block;
            margin: 5px 0;
            animation: pulseGlow 2.5s infinite ease-in-out;
        }
        #clock-box {
            opacity: 0;
            transform: translateY(20px);
            transition: all 1.5s ease-out;
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(12px);
            padding: 15px 20px;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(214, 28, 60, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.9);
            margin-bottom: 20px;
        }
        #clock-box.show {
            opacity: 1;
            transform: translateY(0);
        }
        .clock-label {
            font-size: 0.85rem;
            color: #8c666b;
            margin-bottom: 5px;
            letter-spacing: 1px;
            text-transform: uppercase;
            font-weight: 600;
        }
        #clock {
            font-size: 1.15rem;
            color: #bd2c42;
            font-weight: 700;
            font-variant-numeric: tabular-nums;
        }
        
        /* 100 Reasons Box Styles */
        #reasons-box {
            opacity: 0;
            transform: translateY(30px);
            transition: all 1.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            background: rgba(255, 255, 255, 0.55);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.7);
            box-shadow: 0 15px 35px rgba(214, 28, 60, 0.08);
            height: 280px;
            padding: 20px;
            overflow-y: auto;
        }
        #reasons-box.show {
            opacity: 1;
            transform: translateY(0);
        }
        #reasons-box h3 {
            margin: 0 0 15px 0;
            color: #bd2c42;
            font-size: 1.2rem;
            font-weight: 700;
            border-bottom: 2px dashed rgba(189, 44, 66, 0.2);
            padding-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .reason-item {
            font-size: 0.95rem;
            color: #5c4346;
            line-height: 1.6;
            margin-bottom: 12px;
            padding-bottom: 8px;
            border-bottom: 1px solid rgba(214, 28, 60, 0.05);
            display: flex;
            align-items: flex-start;
            transition: transform 0.2s ease;
        }
        .reason-item:hover {
            transform: translateX(5px);
            color: #be1a25;
        }
        .reason-number {
            font-weight: 700;
            color: #d61c3c;
            margin-right: 10px;
            min-width: 25px;
        }

        /* Scrollbar Styling */
        #reasons-box::-webkit-scrollbar {
            width: 6px;
        }
        #reasons-box::-webkit-scrollbar-track {
            background: transparent;
        }
        #reasons-box::-webkit-scrollbar-thumb {
            background: rgba(214, 28, 60, 0.3);
            border-radius: 10px;
        }

        #canvas-panel {
            width: 52%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }
        canvas {
            cursor: pointer;
            filter: drop-shadow(0 15px 40px rgba(190, 26, 37, 0.12));
        }
        #click-hint {
            position: absolute;
            bottom: 60px;
            font-size: 1.1rem;
            color: #bd2c42;
            background: rgba(255, 255, 255, 0.85);
            padding: 12px 30px;
            border-radius: 25px;
            box-shadow: 0 8px 20px rgba(214, 28, 60, 0.1);
            animation: bounce 2s infinite;
            pointer-events: none;
            font-weight: 600;
            letter-spacing: 0.5px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        @keyframes pulseGlow {
            0%, 100% { transform: scale(1); text-shadow: 0 0 10px rgba(214, 28, 60, 0.1); }
            50% { transform: scale(1.05); text-shadow: 0 0 20px rgba(214, 28, 60, 0.35); }
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-12px); }
            60% { transform: translateY(-6px); }
        }
    </style>
</head>
<body>

    <audio id="myAudio" loop>
        <source src="aud.mp3" type="audio/mp3">
    </audio>

    <div id="container">
        <div id="text-panel">
            <div id="message" class="typewriter-text"></div>
            
            <div id="clock-box">
                <div class="clock-label">🍂 Days of Pure Happiness Together 🌸</div>
                <div id="clock"></div>
            </div>

            <div id="reasons-box">
                <h3>✨ You once asked me why I love you... So here are 100 reasons why:</h3>
                <div id="reasons-list"></div>
            </div>
        </div>
        
        <div id="canvas-panel">
            <canvas id="treeCanvas" width="620" height="680"></canvas>
            <div id="click-hint">🌸  Azzu please Click here for the Tree to Bloom 🍂</div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('treeCanvas');
        const ctx = canvas.getContext('2d');
        const audio = document.getElementById('myAudio');
        
        let animationStarted = false;
        let branches = [];
        let petals = [];
        let fallingPetals = [];

        const lines = [
            "Happiest Birthday, my LUV!! ✨",
            "Aliza the LOML 🌸", 
            "My Hayati....mi amore...my soul, 💕",
            "I'll give you",
            "all the love 🍂",
            "that one can",
            "ever wish for!"
        ];

        const reasonsText = [
            "Your smile makes my world brighter.", "The way your eyes speak when words fail.", "Your voice feels like home.", "You understand my silence.", "You make even the ordinary feel special.", "The warmth of your hug is my safe place.", "Your laughter is my favorite melody.", "You never judge me, even at my worst.", "You complete my incomplete thoughts.", "You love me in ways I never knew I needed.", "Your presence turns my bad days good.", "The way you hold my hand makes me feel secure.", "You remember the little things about me.", "You know my fears yet never make me feel weak.", "Your love feels effortless, yet so deep.", "The way you listen, even when I ramble.", "Your heart is as beautiful as your face.", "You bring out the best in me.", "Your patience with me, even when I'm difficult.", "The way you wipe away my tears.", "You never let me feel alone.", "Your love makes me believe in forever.", "You make me feel important without trying.", "Your kindness makes the world better.", "The way you say my name sounds different.", "You are my peace in this chaotic world.", "The way you trust me without conditions.", "You see beauty in my flaws.", "You remind me to love myself too.", "The way you laugh at my stupid jokes.", "You bring meaning to my existence.", "You make love feel like poetry.", "The way you support my dreams.", "Your heartbeat is my favorite sound.", "You make me believe in magic.", "The way you look at me with love.", "You love me even when I'm unlovable.", "The way you remember our special moments.", "You feel like my missing piece.", "Your touch calms my storms.", "You never give up on me.", "You make the nights feel less lonely.", "You inspire me to be a better person.", "Your love is my greatest strength.", "You don't need words to make me feel loved.", "You make my dreams sweeter.", "Every song reminds me of you.", "Your love is my safe haven.", "You make even silence feel comforting.", "You never let me fight my battles alone.", "Your presence is the best gift.", "You never let me feel invisible.", "You bring color to my dull days.", "Your love is my greatest adventure.", "You know my unspoken words.", "You love me, not just my happiness.", "You never make me feel less.", "Your love makes life worth it.", "You make distance feel smaller.", "Your love is louder than any fear.", "You are my constant in an uncertain world.", "You believe in me when I don't.", "Your love makes my heart race.", "You make pain feel temporary.", "You hold my heart gently.", "You see my scars and love me more.", "Your love is a forever kind of thing.", "You love me on my worst days.", "The way you fit perfectly in my arms.", "You never make love feel heavy.", "You turn ordinary moments into magic.", "You make even the stars jealous.", "You bring warmth to my cold heart.", "Your love feels like a soft whisper.", "You are my reason to believe in love.", "The way your love never fades.", "You are my always and forever.", "Your love is my favorite feeling.", "The way your presence feels like home.", "You make even my demons quiet.", "Your love is my favorite memory.", "The way you make every goodbye hard.", "You make life a little more beautiful.", "You bring hope to my darkest days.", "Your love is my greatest treasure.", "The way you make me feel alive.", "You make forever feel too short.", "Your love is my sweetest addiction.", "You never let me feel replaceable.", "You make every heartbeat count.", "Your love is my strongest prayer.", "You make me believe in soulmates.", "The way you make me crave more of you.", "You are my heart's favorite place.", "You make love feel effortless.", "You never let go, even when I push away.", "Your love is my quiet miracle.", "You make every second with you precious.", "You are the love story I always wanted.", "I love you because you are you."
        ];

        class Vector {
            constructor(x, y) { this.x = x; this.y = y; }
            add(v) { return new Vector(this.x + v.x, this.y + v.y); }
            sub(v) { return new Vector(this.x - v.x, this.y - v.y); }
            mult(n) { return new Vector(this.x * n, this.y * n); }
            heading() { return Math.atan2(this.y, this.x); }
            static fromAngle(angle) { return new Vector(Math.cos(angle), Math.sin(angle)); }
        }

        function drawHeartSeed(x, y, size) {
            ctx.save();
            ctx.beginPath();
            ctx.translate(x, y);
            ctx.moveTo(0, 0);
            ctx.bezierCurveTo(-size/2, -size/2, -size, size/3, 0, size);
            ctx.bezierCurveTo(size, size/3, size/2, -size/2, 0, 0);
            ctx.fillStyle = '#be1a25';
            ctx.fill();
            ctx.restore();
        }

        function createBranch(start, v, length, thickness, level) {
            let end = start.add(v.mult(length));
            branches.push({ start, end, currentEnd: start, thickness, level, progress: 0 });
            
            if (level < 5) {
                let numBranches = 2 + Math.floor(Math.random() * 2);
                for (let i = 0; i < numBranches; i++) {
                    let angleChange = (Math.random() - 0.5) * 0.8;
                    let nextV = Vector.fromAngle(v.heading() + angleChange);
                    createBranch(end, nextV, length * 0.72, thickness * 0.62, level + 1);
                }
            } else {
                // Leaf generation using soft pastel autumn and pink color models
                for (let i = 0; i < 6; i++) {
                    petals.push({
                        pos: end.add(new Vector((Math.random() - 0.5) * 60, (Math.random() - 0.5) * 60)),
                        size: 5 + Math.random() * 8,
                        alpha: 0,
                        maxAlpha: 0.6 + Math.random() * 0.4,
                        scale: 0,
                        delay: Math.random() * 1500,
                        color: Math.random() > 0.5 ? '#e0364c' : (Math.random() > 0.5 ? '#ff7386' : '#fca34d') // Autumn mixed hue palette
                    });
                }
            }
        }

        ctx.lineCap = 'round';
        const startPoint = new Vector(canvas.width / 2, canvas.height - 20);
        createBranch(startPoint, new Vector(0, -1), 125, 16, 0);
        drawHeartSeed(canvas.width / 2, canvas.height / 2 - 20, 20);

        canvas.addEventListener('click', () => {
            if (animationStarted) return;
            animationStarted = true;
            audio.play().catch(e => console.log("Audio pipeline loaded."));
            document.getElementById('click-hint').style.display = 'none';
            animate();
        });

        let textTriggered = false;

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            let allBranchesDone = true;

            // Draw Branches
            branches.forEach(b => {
                if (b.level === 0 || branches.filter(p => p.end === b.start)[0]?.progress >= 1) {
                    if (b.progress < 1) {
                        b.progress += 0.012;
                        let diff = b.end.sub(b.start);
                        b.currentEnd = b.start.add(diff.mult(b.progress));
                        allBranchesDone = false;
                    }
                } else {
                    allBranchesDone = false;
                }
                ctx.beginPath();
                ctx.moveTo(b.start.x, b.start.y);
                ctx.lineTo(b.currentEnd.x, b.currentEnd.y);
                ctx.strokeStyle = `rgba(92, 53, 57, ${Math.min(1, b.progress + 0.4)})`;
                ctx.lineWidth = b.thickness;
                ctx.stroke();
            });

            // Draw Blossoming Petals
            if (allBranchesDone) {
                petals.forEach(p => {
                    if (p.delay > 0) {
                        p.delay -= 16;
                    } else {
                        if (p.scale < 1) p.scale += 0.02;
                        if (p.alpha < p.maxAlpha) p.alpha += 0.02;
                    }
                    
                    ctx.save();
                    ctx.globalAlpha = p.alpha;
                    ctx.translate(p.pos.x, p.pos.y);
                    ctx.beginPath();
                    ctx.moveTo(0, 0);
                    ctx.bezierCurveTo(-p.size*p.scale/2, -p.size*p.scale/2, -p.size*p.scale, p.size*p.scale/3, 0, p.size*p.scale);
                    ctx.bezierCurveTo(p.size*p.scale, p.size*p.scale/3, p.size*p.scale/2, -p.size*p.scale/2, 0, 0);
                    ctx.fillStyle = p.color;
                    ctx.fill();
                    ctx.restore();
                });

                // Spawn continuous shredding autumn petal system logic
                if (Math.random() < 0.05 && fallingPetals.length < 60) {
                    fallingPetals.push({
                        x: Math.random() * canvas.width,
                        y: 100 + Math.random() * 300,
                        size: 4 + Math.random() * 6,
                        speedY: 0.8 + Math.random() * 1.2,
                        speedX: (Math.random() - 0.3) * 1,
                        rot: Math.random() * Math.PI,
                        rotSpeed: (Math.random() - 0.5) * 0.03,
                        color: Math.random() > 0.5 ? '#ff7386' : '#fca34d'
                    });
                }

                // Render continuous shredding falling petal animation loop arrays
                fallingPetals.forEach((fp, index) => {
                    fp.y += fp.speedY;
                    fp.x += fp.speedX;
                    fp.rot += fp.rotSpeed;

                    if (fp.y > canvas.height) {
                        fallingPetals.splice(index, 1);
                    }

                    ctx.save();
                    ctx.translate(fp.x, fp.y);
                    ctx.rotate(fp.rot);
                    ctx.beginPath();
                    ctx.moveTo(0, 0);
                    ctx.bezierCurveTo(-fp.size/2, -fp.size/2, -fp.size, fp.size/3, 0, fp.size);
                    ctx.bezierCurveTo(fp.size, fp.size/3, fp.size/2, -fp.size/2, 0, 0);
                    ctx.fillStyle = fp.color;
                    ctx.fill();
                    ctx.restore();
                });

                if (!textTriggered) {
                    textTriggered = true;
                    startTyping();
                }
            } else {
                drawHeartSeed(canvas.width / 2, canvas.height / 2 - 20, 5);
            }

            requestAnimationFrame(animate);
        }

        function startTyping() {
            const msgContainer = document.getElementById('message');
            let lineIdx = 0;
            let charIdx = 0;

            function type() {
                if (lineIdx < lines.length) {
                    if (charIdx === 0) {
                        if (lineIdx === 1) {
                            msgContainer.innerHTML += `<span class="highlight-name"></span><br/>`;
                        } else {
                            msgContainer.innerHTML += `<span></span><br/>`;
                        }
                    }

                    const targetSpan = msgContainer.querySelector(lineIdx === 1 ? '.highlight-name' : `span:nth-last-of-type(1)`);
                    targetSpan.innerHTML += lines[lineIdx][charIdx];
                    charIdx++;

                    if (charIdx < lines[lineIdx].length) {
                        setTimeout(type, 70);
                    } else {
                        lineIdx++;
                        charIdx = 0;
                        setTimeout(type, 350);
                    }
                } else {
                    document.getElementById('clock-box').classList.add('show');
                    populateAndShowReasons();
                    setInterval(updateClock, 1000);
                    updateClock();
                }
            }
            type();
        }

        function populateAndShowReasons() {
            const container = document.getElementById('reasons-list');
            reasonsText.forEach((reason, index) => {
                const item = document.createElement('div');
                item.className = 'reason-item';
                item.innerHTML = `<span class="reason-number">${index + 1}.</span> <span>${reason}</span>`;
                container.appendChild(item);
            });
            document.getElementById('reasons-box').classList.add('show');
        }

        function updateClock() {
            // Target locked directly on July 21, 2025 metric sequence line matrix
            const startDate = new Date(2025, 6, 21, 0, 0, 0); 
            const now = new Date();
            const diff = now - startDate;

            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);

            document.getElementById('clock').innerHTML = `${days} Days, ${hours} Hours, ${minutes} Minutes, ${seconds} Seconds`;
        }
    </script>
</body>
</html>
