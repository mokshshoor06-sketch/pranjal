<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Love for Pranjal</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #ffe6f2;
            color: #333;
            text-align: center;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }
        .slide {
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            padding: 20px;
            box-sizing: border-box;
        }
        .active {
            display: block;
        }
        h1, h2 {
            color: #ff69b4;
        }
        .love-letter {
            max-width: 600px;
            margin: 0 auto;
            font-size: 18px;
            line-height: 1.6;
        }
        .game {
            margin: 20px auto;
            max-width: 400px;
        }
        input, button {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
        }
        .buttons {
            margin-top: 20px;
        }
        .no-button, .yes-button {
            background-color: #ff69b4; /* Same color for both */
            color: white;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            position: relative; /* For moving the No button */
        }
        .no-button:hover {
            animation: moveAway 0.5s ease-in-out; /* Move away on hover */
        }
        @keyframes moveAway {
            0% { transform: translateX(0); }
            25% { transform: translateX(50px); }
            50% { transform: translateY(-20px); }
            75% { transform: translateX(-50px); }
            100% { transform: translateY(20px); }
        }
        .yes-button:hover {
            background-color: #ff1493;
        }
        .heart {
            font-size: 50px;
            color: #ff69b4;
        }
        .quiz-option {
            display: block;
            margin: 10px auto;
            width: 200px;
        }
        /* Enhanced Envelope Styles */
        .envelope {
            width: 350px;
            height: 250px;
            background: linear-gradient(135deg, #f8f8f8 0%, #e0e0e0 100%);
            border: 3px solid #d4a574;
            margin: 50px auto;
            position: relative;
            cursor: pointer;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .envelope:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        .envelope::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 0;
            border-left: 175px solid transparent;
            border-right: 175px solid transparent;
            border-top: 125px solid #c4a484;
        }
        .envelope::after {
            content: '';
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 50px;
            background: radial-gradient(circle, #ff69b4 0%, #d4a574 70%);
            border-radius: 50%;
            border: 2px solid #8b4513;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.3);
        }
        .envelope-text {
            position: absolute;
            top: 60%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 24px;
            color: #8b4513;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }
        .envelope-flap {
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 0;
            border-left: 175px solid transparent;
            border-right: 175px solid transparent;
            border-top: 125px solid rgba(196, 164, 132, 0.8);
            transition: border-top-color 0.3s ease;
        }
        .envelope:hover .envelope-flap {
            border-top-color: rgba(196, 164, 132, 1);
        }
        /* Floating Hearts Animation */
        .floating-hearts {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }
        .heart-emoji {
            position: absolute;
            font-size: 30px;
            color: #ff69b4;
            animation: float 6s linear infinite;
            opacity: 0.7;
        }
        .heart-emoji:nth-child(1) { left: 10%; animation-delay: 0s; }
        .heart-emoji:nth-child(2) { left: 20%; animation-delay: 1s; }
        .heart-emoji:nth-child(3) { left: 30%; animation-delay: 2s; }
        .heart-emoji:nth-child(4) { left: 40%; animation-delay: 3s; }
        .heart-emoji:nth-child(5) { left: 50%; animation-delay: 4s; }
        .heart-emoji:nth-child(6) { left: 60%; animation-delay: 5s; }
        .heart-emoji:nth-child(7) { left: 70%; animation-delay: 0s; }
        .heart-emoji:nth-child(8) { left: 80%; animation-delay: 1s; }
        .heart-emoji:nth-child(9) { left: 90%; animation-delay: 2s; }
        .heart-emoji:nth-child(10) { left: 100%; animation-delay: 3s; }
        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); }
            100% { transform: translateY(-100px) rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Floating Hearts on All Slides -->
    <div class="floating-hearts">
        <div class="heart-emoji">❤️</div>
        <div class="heart-emoji">💖</div>
        <div class="heart-emoji">❤️</div>
        <div class="heart-emoji">💖</div>
        <div class="heart-emoji">❤️</div>
        <div class="heart-emoji">💖</div>
        <div class="heart-emoji">❤️</div>
        <div class="heart-emoji">💖</div>
        <div class="heart-emoji">❤️</div>
        <div class="heart-emoji">💖</div>
    </div>

    <!-- New Slide 1: Closed Letter (Envelope) -->
    <div id="slide1" class="slide active">
        <h1>❤️ Click the Letter to Open ❤️</h1>
        <div class="envelope" onclick="nextSlide()">
            <div class="envelope-flap"></div>
            <div class="envelope-text">For My Love 💌</div>
        </div>
    </div>

    <!-- Slide 2: Love Letter (Original Slide 1) -->
    <div id="slide2" class="slide">
        <h1>❤️ A Love Letter for Pranjal ❤️</h1>
        <div class="love-letter">
            <p>Dear Pranjal, 💕</p>
            <p>From the moment I met you, my world has been filled with joy and light. Your smile brightens my day, and your laughter is the sweetest music. I cherish every moment we spend together, and I can't imagine my life without you. You are my everything, my love, my princess. ❤️</p>
            <p>With all my heart,<br>Moksh 💖</p>
        </div>
        <button onclick="nextSlide()">Next ❤️</button>
    </div>

    <!-- Slide 3: Cute Game (Original Slide 2) -->
    <div id="slide3" class="slide">
        <h1>❤️ A Cute Romantic Quiz! ❤️</h1>
        <p>Answer this question to win a sweet message: What is the color of love? (Hint: It's not just red!) 💕</p>
        <div class="game">
            <button class="quiz-option" onclick="checkAnswer('red')">Red ❤️</button>
            <button class="quiz-option" onclick="checkAnswer('pink')">Pink 💖</button>
            <button class="quiz-option" onclick="checkAnswer('blue')">Blue 💙</button>
            <button class="quiz-option" onclick="checkAnswer('all')">All of them 🌈</button>
            <p id="result"></p>
        </div>
        <button onclick="nextSlide()" style="display:none;" id="gameNext">Next ❤️</button>
    </div>

    <!-- Slide 4: I Love You with Buttons (Original Slide 3) -->
    <div id="slide4" class="slide">
        <h1 class="heart">❤️</h1>
        <h2>I Love You 💕</h2>
        <div class="buttons">
            <button class="no-button" id="noBtn">No 😢</button>
            <button class="yes-button" onclick="nextSlide()">Yes ❤️</button>
        </div>
    </div>

    <!-- Slide 5: Final Message (Original Slide 4) -->
    <div id="slide5" class="slide">
        <h1 class="heart">❤️</h1>
        <h2>I Love You 💕</h2>
        <p>Happy 'Most Radiant Princess Day', my love, the princess of my heart. I wish you the most enchanting and beautiful day. 💖</p>
        <p>💖 You're the best! 💖</p>
    </div>

    <script>
        let currentSlide = 1;
        const totalSlides = 5;

        function nextSlide() {
            if (currentSlide < totalSlides) {
                document.getElementById('slide' + currentSlide).classList.remove('active');
                currentSlide++;
                document.getElementById('slide' + currentSlide).classList.add('active');
            }
        }

        function checkAnswer(answer) {
            const result = document.getElementById('result');
            if (answer === 'all') {
                result.textContent = "Correct! Love comes in all colors, just like you make my world colorful. 💕";
                document.getElementById('gameNext').style.display = 'inline';
            } else {
                result.textContent = "Not quite! Try again. ❤️";
            }
        }
    </script>
</body>
</html>
