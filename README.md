<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Für Dich ❤️</title>
    <style>
        :root {
            --primary-color: #ff6b9d;
            --secondary-color: #c44569;
            --bg-gradient-1: #ee9ca7;
            --bg-gradient-2: #ffdde1;
            --text-dark: #2c3e50;
            --text-light: #ffffff;
        }

        {
            margin: 0;
            padding: 0;
            box-sizing: border-box }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, var(--bg-gradient-1) 0%, var(--bg-gradient-2) 100%);
            min-height: 100vh;
            overflow-x: hidden;
            color: var(--text-dark);
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 60px 20px;
            animation: fadeInDown 1s ease-out;
        }

        .hero h1 {
            font-size: 3.5rem;
            color: var(--secondary-color);
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        .hero p {
            font-size: 1.3rem;
            color: var(--text-dark);
            opacity: 0.9;
        }

        /* Floating Hearts Animation */
        .hearts-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            overflow: hidden;
        }

        .heart {
            position: absolute;
            font-size: 2rem;
            opacity: 0;
            animation: floatHeart 8s infinite;
        }

        @keyframes floatHeart {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.8;
            }
            90% {
                opacity: 0.8;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Card Styles */
        .card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 40px;
            margin: 30px 0;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            animation: fadeInUp 1s ease-out;
            backdrop-filter: blur(10px);
        }

        .card h2 {
            color: var(--secondary-color);
            font-size: 2rem;
            margin-bottom: 20px;
            text-align: center;
        }

        .card p {
            line-height: 1.8;
            font-size: 1.1rem;
            margin-bottom: 15px;
        }

        /* Reasons Grid */
        .reasons-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .reason-card {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--text-light);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transform: translateY(0);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }

        .reason-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(196, 69, 105, 0.4);
        }

        .reason-card .icon {
            font-size: 3rem;
            margin-bottom: 15px;
        }

        .reason-card h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .reason-card p {
            font-size: 0.95rem;
            opacity: 0.9;
        }

        /* Photo Gallery */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 30px;
        }

        .gallery-item {
            aspect-ratio: 1;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 4rem;
            cursor: pointer;
            transition: transform 0.3s ease;
            overflow: hidden;
            position: relative;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        /* Countdown Timer */
        .countdown {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            margin-top: 30px;
        }

        .countdown-item {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
        }

        .countdown-item .number {
            font-size: 2.5rem;
            font-weight: bold;
            display: block;
        }

        .countdown-item .label {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-top: 5px;
        }

        /* Button */
        .btn {
            display: inline-block;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-size: 1.1rem;
            font-weight: 600;
            margin: 20px auto;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
            border: none;
            display: block;
            text-align: center;
            max-width: 300px;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(196, 69, 105, 0.4);
        }

        /* Message Box */
        .message-box {
            background: white;
            border-radius: 15px;
            padding: 20px;
            margin-top: 20px;
            border: 2px solid var(--primary-color);
            display: none;
        }

        .message-box.active {
            display: block;
            animation: fadeInUp 0.5s ease-out;
        }

        .message-box textarea {
            width: 100%;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 10px;
            font-family: inherit;
            font-size: 1rem;
            resize: vertical;
            min-height: 120px;
        }

        /* Animations */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Valentine Question */
        .valentine-section {
            text-align: center;
            padding: 40px 20px;
        }

        .valentine-section h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: var(--secondary-color);
        }

        .valentine-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .valentine-btn {
            padding: 20px 50px;
            font-size: 1.5rem;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
        }

        .valentine-btn.yes {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
        }

        .valentine-btn.yes:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 30px rgba(196, 69, 105, 0.5);
        }

        .valentine-btn.no {
            background: #e0e0e0;
            color: #666;
            position: relative;
        }

        .valentine-btn.no:hover {
            transform: scale(0.9);
        }

        .valentine-response {
            margin-top: 30px;
            font-size: 1.5rem;
            color: var(--secondary-color);
            font-weight: bold;
            display: none;
        }

        .valentine-response.show {
            display: block;
            animation: fadeInUp 0.5s ease-out;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .card {
                padding: 25px;
            }
            
            .countdown {
                grid-template-columns: repeat(2, 1fr);
            }

            .valentine-section h2 {
                font-size: 2rem;
            }

            .valentine-btn {
                padding: 15px 35px;
                font-size: 1.2rem;
            }

            .gallery {
                grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .card {
                padding: 20px;
            }

            .card h2 {
                font-size: 1.5rem;
            }

            .reasons-grid {
                grid-template-columns: 1fr;
            }

            .valentine-buttons {
                flex-direction: column;
                gap: 15px;
            }

            .valentine-btn {
                width: 100%;
                max-width: 300px;
            }
        }
    </style>
</head>
<body>
    <!-- Floating Hearts Background -->
    <div class="hearts-container" id="heartsContainer"></div>

    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <h1>Für Dich ❤️</h1>
            <p>Weil du etwas ganz Besonderes bist</p>
        </div>

        <!-- Love Letter Card -->
        <div class="card">
            <h2>💌 Meine Liebe</h2>
            <p>Liebe Leya,</p>
            <p>diese Website ist zeigt wie sehr ich dich lieb hab</p>
            <p>Sie zeigt die schönsten erinnerungen der Letzen Wochen</p>
            <p>Ich habe dich unfassbar doll lieb <3 </p>
            <p style="text-align: right; margin-top: 30px;">Für immer dein,<br><strong>Jonas</strong></p>
        </div>

        <!-- Reasons Why I Love You -->
        <div class="card">
            <h2>💝 Gründe, warum ich dich liebe</h2>
            <div class="reasons-grid">
                <div class="reason-card">
                    <div class="icon">😊</div>
                    <h3>Dein Lächeln</h3>
                    <p>Es erhellt meinen ganzen Tag</p>
                </div>
                <div class="reason-card">
                    <div class="icon">💖</div>
                    <h3>Dein Herz</h3>
                    <p>So groß und liebevoll</p>
                </div>
                <div class="reason-card">
                    <div class="icon">✨</div>
                    <h3>Deine Art</h3>
                    <p>Einzigartig und wundervoll</p>
                </div>
                <div class="reason-card">
                    <div class="icon">🌟</div>
                    <h3>Deine Stärke</h3>
                    <p>Du inspirierst mich jeden Tag</p>
                </div>
                <div class="reason-card">
                    <div class="icon">🎵</div>
                    <h3>Dein Lachen</h3>
                    <p>Die schönste Melodie</p>
                </div>
                <div class="reason-card">
                    <div class="icon">🌈</div>
                    <h3>Deine Energie</h3>
                    <p>Du machst alles bunter</p>
                </div>
            </div>
        </div>

        <!-- Our Memories -->
        <div class="card">
            <h2>📸 Unsere Erinnerungen</h2>
            <p style="text-align: center; margin-bottom: 20px;">Hier könntest du Fotos einfügen!</p>
            <div class="gallery">
                <div class="gallery-item">
                    <img src="https://agi-prod-file-upload-public-main-use1.s3.amazonaws.com/932022f2-d755-4309-a68e-f15e9899a801" alt="Ski-Abenteuer in den Alpen" />
                </div>
                <div class="gallery-item">
                    <img src="https://agi-prod-file-upload-public-main-use1.s3.amazonaws.com/a7919ff5-97fa-400a-b239-dbdfdec45960" alt="Gemütlich vor dem Weihnachtsbaum" />
                </div>
                <div class="gallery-item">
                    <img src="https://agi-prod-file-upload-public-main-use1.s3.amazonaws.com/445d2fbf-d6a4-4b05-9b35-44795cd69569" alt="Auf der Piste" />
                </div>
                <div class="gallery-item">
                    <img src="https://agi-prod-file-upload-public-main-use1.s3.amazonaws.com/7c90b730-d5de-4d34-b0fc-f552d14efe69" alt="Stadtbummel" />
                </div>
            </div>
        </div>

        <!-- Countdown to Special Day -->
        <div class="card">
            <h2>⏰ Countdown bis zu unserem nächsten Treffen</h2>
            <div class="countdown" id="countdown">
                <div class="countdown-item">
                    <span class="number" id="days">0</span>
                    <span class="label">Tage</span>
                </div>
                <div class="countdown-item">
                    <span class="number" id="hours">0</span>
                    <span class="label">Stunden</span>
                </div>
                <div class="countdown-item">
                    <span class="number" id="minutes">0</span>
                    <span class="label">Minuten</span>
                </div>
                <div class="countdown-item">
                    <span class="number" id="seconds">0</span>
                    <span class="label">Sekunden</span>
                </div>
            </div>
        </div>

        <!-- Interactive Button -->
        <div class="card" style="text-align: center;">
            <h2>💕 Klick mich!</h2>
            <button class="btn" onclick="showMessage()">Eine besondere Nachricht für dich</button>
            <div class="message-box" id="messageBox">
                <p style="font-size: 1.5rem; text-align: center; color: var(--secondary-color); font-weight: bold;">
                    Du bist die Witzigste Person die ich kenne
                </p>
                <p style="text-align: center; margin-top: 15px;">
                    Danke, dass es dich gibt. Ich liebe dich von ganzem Herzen! ❤️
                </p>
            </div>
        </div>

        <!-- Valentine Question -->
        <div class="card valentine-section">
            <h2>💝 Eine wichtige Frage...</h2>
            <p style="font-size: 1.5rem; margin: 20px 0;">Willst du mein Valentine sein? 🌹</p>
            <div class="valentine-buttons">
                <button class="valentine-btn yes" onclick="valentineAnswer('yes')">Ja! ❤️</button>
                <button class="valentine-btn no" onclick="valentineAnswer('no')">Nein 😢</button>
            </div>
            <div class="valentine-response" id="valentineResponse"></div>
        </div>
    </div>

    <script>
        // Floating Hearts Animation
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + '%';
            heart.style.animationDelay = Math.random() * 3 + 's';
            heart.style.animationDuration = (Math.random() * 3 + 5) + 's';
            document.getElementById('heartsContainer').appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 8000);
        }

        setInterval(createHeart, 800);

        // Countdown Timer
        function updateCountdown() {
            // Setze hier dein Zieldatum (Jahr, Monat-1, Tag, Stunde, Minute)
            const targetDate = new Date(2026, 1, 13, 14, 0, 0); // 13. Februar 2026, 14:00 Uhr
            const now = new Date();
            const difference = targetDate - now;

            if (difference > 0) {
                const days = Math.floor(difference / (1000 * 60 * 60 * 24));
                const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((difference % (1000 * 60)) / 1000);

                document.getElementById('days').textContent = days;
                document.getElementById('hours').textContent = hours;
                document.getElementById('minutes').textContent = minutes;
                document.getElementById('seconds').textContent = seconds;
            } else {
                document.getElementById('days').textContent = '0';
                document.getElementById('hours').textContent = '0';
                document.getElementById('minutes').textContent = '0';
                document.getElementById('seconds').textContent = '0';
            }
        }

        setInterval(updateCountdown, 1000);
        updateCountdown();

        // Show Message Function
        function showMessage() {
            const messageBox = document.getElementById('messageBox');
            messageBox.classList.toggle('active');
        }

        // Add animation to reason cards on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.6s ease-out forwards';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.card').forEach(card => {
            observer.observe(card);
        });

        // Valentine Answer Function
        let noClickCount = 0;
        function valentineAnswer(answer) {
            const responseDiv = document.getElementById('valentineResponse');
            const noBtn = document.querySelector('.valentine-btn.no');
            
            if (answer === 'yes') {
                responseDiv.innerHTML = '🎉 Yay! Du machst mich zum glücklichsten Menschen! ❤️❤️❤️<br><br>Ich liebe dich so sehr vom Kopf bis zum Stinkezeh! 💕';
                responseDiv.classList.add('show');
                
                // Create confetti effect
                for (let i = 0; i < 50; i++) {
                    setTimeout(() => {
                        const heart = document.createElement('div');
                        heart.classList.add('heart');
                        heart.innerHTML = '❤️';
                        heart.style.left = Math.random() * 100 + '%';
                        heart.style.fontSize = (Math.random() * 2 + 1) + 'rem';
                        document.getElementById('heartsContainer').appendChild(heart);
                        
                        setTimeout(() => heart.remove(), 8000);
                    }, i * 50);
                }
            } else {
                noClickCount++;
                if (noClickCount === 1) {
                    responseDiv.innerHTML = '😢 Bist du sicher? Versuch es nochmal...';
                    noBtn.textContent = 'Wirklich nicht? 🥺';
                } else if (noClickCount === 2) {
                    responseDiv.innerHTML = '💔 Bitte... denk nochmal darüber nach! 🙏';
                    noBtn.textContent = 'Vielleicht doch? 💝';
                } else {
                    responseDiv.innerHTML = '😭 Ich warte hier, bis du "Ja" sagst! ❤️';
                    noBtn.style.display = 'none';
                }
                responseDiv.classList.add('show');
            }
        }
    </script>
</body>
</html>
