<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>☆ Bunny Paw Fortune Teller ☆ ~*Internet Checkpoint*~</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=VT323&family=Press+Start+2P&display=swap" rel="stylesheet">
    <style>
        :root {
            --hot-pink: #ff69b4;
            --chrome-light: #e0e0e0;
            --chrome-dark: #808080;
            --baby-blue: #b4d7f0;
            --lime: #ccff00;
            --purple-glow: #d946ef;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #000;
            background-image: 
                url("data:image/svg+xml,%3Csvg width='40' height='40' viewBox='0 0 40 40' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='%23ff69b4' fill-opacity='0.1' fill-rule='evenodd'%3E%3Cpath d='M0 0h40v40H0V0zm20 20h20v20H20V20zM0 20h20v20H0V20zM20 0h20v20H20V0z'/%3E%3C/g%3E%3C/svg%3E"),
                radial-gradient(circle at 20% 50%, rgba(255, 0, 255, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(0, 255, 255, 0.1) 0%, transparent 50%);
            font-family: 'VT323', monospace;
            color: #fff;
            overflow-x: hidden;
            min-height: 100vh;
            cursor: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3Ctext y='20' font-size='20'%3E🐰%3C/text%3E%3C/svg%3E"), auto;
        }

        /* Sparkle background animation */
        .sparkle {
            position: fixed;
            pointer-events: none;
            animation: sparkleFall linear infinite;
            z-index: 1;
            opacity: 0.6;
            font-size: 14px;
        }

        @keyframes sparkleFall {
            0% { transform: translateY(-10vh) rotate(0deg); opacity: 0; }
            10% { opacity: 0.8; }
            90% { opacity: 0.8; }
            100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
        }

        /* Main Container */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 10;
        }

        /* Header */
        .header {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }

        .header h1 {
            font-family: 'Press Start 2P', cursive;
            font-size: clamp(1rem, 4vw, 1.8rem);
            background: linear-gradient(to bottom, #fff 0%, #ff69b4 50%, #d946ef 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 20px rgba(255, 105, 180, 0.5);
            letter-spacing: -1px;
            line-height: 1.4;
            animation: glitch 4s infinite;
        }

        .header .subtitle {
            color: var(--lime);
            font-size: 1.3rem;
            margin-top: 10px;
            text-shadow: 0 0 10px var(--lime);
            animation: pulse 2s infinite;
        }

        .construction-tape {
            background: repeating-linear-gradient(
                45deg,
                #ffcc00,
                #ffcc00 10px,
                #000 10px,
                #000 20px
            );
            color: #000;
            font-family: 'Press Start 2P', cursive;
            font-size: 0.6rem;
            padding: 5px;
            margin: 10px 0;
            text-align: center;
            border: 2px solid #fff;
            box-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
        }

        @keyframes glitch {
            0%, 90%, 100% { transform: translate(0); }
            91% { transform: translate(-2px, 2px); }
            92% { transform: translate(2px, -2px); }
            93% { transform: translate(0); }
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.6; }
        }

        /* The Bunny Paw */
        .paw-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 40px 0;
            position: relative;
        }

        .bunny-paw {
            width: 280px;
            height: 320px;
            position: relative;
            cursor: pointer;
            transition: transform 0.2s;
            filter: drop-shadow(0 0 20px rgba(255, 105, 180, 0.4));
        }

        .bunny-paw:hover {
            transform: scale(1.05);
        }

        .bunny-paw:active {
            transform: scale(0.95);
        }

        .paw-pad-main {
            width: 180px;
            height: 200px;
            background: radial-gradient(ellipse at 30% 30%, #ffe4e9, #ffb6c1, #ff69b4);
            border-radius: 50% 50% 45% 45%;
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            box-shadow: 
                inset -10px -10px 20px rgba(189, 52, 146, 0.3),
                inset 10px 10px 20px rgba(255, 255, 255, 0.5),
                0 10px 30px rgba(255, 105, 180, 0.3);
            border: 3px solid #ff69b4;
        }

        .paw-pad-main::after {
            content: '🐾';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 3rem;
            opacity: 0.3;
        }

        .toe {
            width: 70px;
            height: 100px;
            background: linear-gradient(135deg, #ffe4e9 0%, #ffb6c1 50%, #ff69b4 100%);
            border-radius: 50% 50% 40% 40%;
            position: absolute;
            top: 0;
            border: 2px solid #ff1493;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 
                inset -5px -5px 10px rgba(189, 52, 146, 0.3),
                0 5px 15px rgba(255, 20, 147, 0.2);
        }

        .toe:hover {
            transform: translateY(-10px) scale(1.1);
            box-shadow: 0 0 20px var(--hot-pink);
            z-index: 10;
        }

        .toe::before {
            content: '';
            width: 25px;
            height: 35px;
            background: rgba(255, 255, 255, 0.4);
            border-radius: 50%;
            position: absolute;
            top: 15px;
            left: 50%;
            transform: translateX(-50%);
        }

        .toe-1 { left: 10px; transform: rotate(-15deg); }
        .toe-2 { left: 70px; transform: rotate(-5deg); top: -10px; }
        .toe-3 { right: 70px; transform: rotate(5deg); top: -10px; }
        .toe-4 { right: 10px; transform: rotate(15deg); }

        .click-hint {
            text-align: center;
            color: var(--lime);
            font-size: 1.2rem;
            margin-top: 10px;
            animation: blink 1.5s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }

        /* Fortune Box */
        .fortune-box {
            background: rgba(0, 0, 0, 0.7);
            border: 3px solid var(--hot-pink);
            border-radius: 8px;
            padding: 20px;
            margin: 20px auto;
            max-width: 600px;
            min-height: 100px;
            position: relative;
            box-shadow: 
                0 0 20px rgba(255, 105, 180, 0.3),
                inset 0 0 20px rgba(255, 105, 180, 0.1);
            font-family: 'VT323', monospace;
            font-size: 1.5rem;
            color: #fff;
            text-align: center;
            image-rendering: pixelated;
        }

        .fortune-box::before {
            content: '▼ FORTUNE TERMINAL v2.0 ▼';
            display: block;
            background: linear-gradient(to right, var(--hot-pink), var(--purple-glow));
            color: #000;
            font-family: 'Press Start 2P', cursive;
            font-size: 0.6rem;
            padding: 5px;
            margin: -20px -20px 15px -20px;
            border-bottom: 2px solid var(--hot-pink);
        }

        .fortune-text {
            line-height: 1.4;
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .cursor-blink {
            display: inline-block;
            width: 10px;
            height: 1.2em;
            background: var(--lime);
            animation: cursorBlink 1s infinite;
            vertical-align: text-bottom;
            margin-left: 2px;
        }

        @keyframes cursorBlink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        /* Chrome Panel - Guestbook */
        .chrome-panel {
            background: linear-gradient(180deg, 
                rgba(224, 224, 224, 0.15) 0%, 
                rgba(128, 128, 128, 0.1) 100%);
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 12px;
            padding: 20px;
            margin: 30px 0;
            position: relative;
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.3),
                inset 0 1px 0 rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(4px);
        }

        .chrome-panel::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 25px;
            background: linear-gradient(to bottom, rgba(255,255,255,0.2), transparent);
            border-radius: 10px 10px 0 0;
            pointer-events: none;
        }

        .panel-title {
            font-family: 'Press Start 2P', cursive;
            font-size: 0.8rem;
            color: var(--baby-blue);
            text-align: center;
            margin-bottom: 20px;
            text-shadow: 0 0 10px var(--baby-blue);
        }

        /* Guestbook */
        .guestbook-feed {
            height: 250px;
            overflow-y: auto;
            background: rgba(0, 0, 20, 0.6);
            border: 2px inset rgba(255, 255, 255, 0.2);
            padding: 10px;
            margin-bottom: 15px;
            font-size: 1.1rem;
            scrollbar-width: thin;
            scrollbar-color: var(--hot-pink) rgba(0,0,0,0.3);
        }

        .guestbook-feed::-webkit-scrollbar {
            width: 10px;
        }

        .guestbook-feed::-webkit-scrollbar-track {
            background: rgba(0,0,0,0.3);
        }

        .guestbook-feed::-webkit-scrollbar-thumb {
            background: linear-gradient(to bottom, var(--hot-pink), var(--purple-glow));
            border-radius: 5px;
        }

        .guest-entry {
            padding: 8px;
            margin-bottom: 8px;
            background: rgba(255, 105, 180, 0.1);
            border-left: 3px solid var(--hot-pink);
            animation: slideIn 0.5s ease-out;
        }

        .guest-prefix {
            color: var(--lime);
            font-weight: bold;
        }

        .guest-time {
            color: var(--chrome-dark);
            font-size: 0.9rem;
            float: right;
        }

        @keyframes slideIn {
            from { transform: translateX(-20px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        .guestbook-input {
            display: flex;
            gap: 10px;
        }

        .guestbook-input input {
            flex: 1;
            background: rgba(0, 0, 0, 0.6);
            border: 2px inset rgba(255, 255, 255, 0.2);
            color: #fff;
            padding: 10px;
            font-family: 'VT323', monospace;
            font-size: 1.1rem;
            outline: none;
        }

        .guestbook-input input:focus {
            border-color: var(--hot-pink);
            box-shadow: 0 0 10px rgba(255, 105, 180, 0.3);
        }

        .btn {
            background: linear-gradient(180deg, #ff69b4, #d946ef);
            border: 2px outset #ff69b4;
            color: #fff;
            font-family: 'Press Start 2P', cursive;
            font-size: 0.6rem;
            padding: 10px 15px;
            cursor: pointer;
            text-transform: uppercase;
            transition: all 0.2s;
            text-shadow: 1px 1px 0 rgba(0,0,0,0.5);
        }

        .btn:hover {
            background: linear-gradient(180deg, #ff85c2, #e055f5);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 105, 180, 0.4);
        }

        .btn:active {
            border-style: inset;
            transform: translateY(0);
        }

        /* Visitor Counter */
        .visitor-counter {
            text-align: center;
            margin: 30px 0;
            padding: 15px;
            background: linear-gradient(180deg, #1a1a1a, #0a0a0a);
            border: 3px ridge var(--chrome-dark);
            border-radius: 4px;
            display: inline-block;
            left: 50%;
            position: relative;
            transform: translateX(-50%);
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.1);
        }

        .counter-label {
            font-family: 'Press Start 2P', cursive;
            font-size: 0.5rem;
            color: var(--chrome-dark);
            margin-bottom: 5px;
            display: block;
        }

        .odometer {
            font-family: 'Press Start 2P', cursive;
            font-size: 1.2rem;
            color: #00ff00;
            text-shadow: 0 0 10px rgba(0, 255, 0, 0.5);
            letter-spacing: 4px;
            background: #000;
            padding: 5px 10px;
            border: 2px inset #333;
        }

        /* Secret Button */
        .secret-btn {
            position: fixed;
            bottom: 10px;
            right: 10px;
            width: 20px;
            height: 20px;
            background: transparent;
            border: none;
            cursor: pointer;
            z-index: 1000;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .secret-btn:hover {
            opacity: 0.3;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
        }

        /* Bunny Dance Overlay */
        .dance-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            z-index: 9999;
            display: none;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            font-family: 'Press Start 2P', cursive;
        }

        .dance-overlay.active {
            display: flex;
            animation: bgFlash 0.5s infinite;
        }

        @keyframes bgFlash {
            0%, 100% { background: rgba(255, 0, 255, 0.3); }
            50% { background: rgba(0, 255, 255, 0.3); }
        }

        .dance-bunny {
            font-size: 8rem;
            animation: dance 0.5s infinite;
        }

        @keyframes dance {
            0%, 100% { transform: rotate(-10deg) scale(1); }
            25% { transform: rotate(10deg) scale(1.2); }
            50% { transform: rotate(-10deg) scale(1); }
            75% { transform: rotate(10deg) scale(1.2); }
        }

        .dance-text {
            color: var(--lime);
            font-size: 1.5rem;
            margin-top: 20px;
            text-shadow: 0 0 20px var(--lime);
            animation: shake 0.3s infinite;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }

        /* Audio Control */
        .audio-control {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 100;
            background: rgba(0, 0, 0, 0.7);
            border: 2px solid var(--hot-pink);
            border-radius: 50%;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1.5rem;
            transition: all 0.3s;
            box-shadow: 0 0 15px rgba(255, 105, 180, 0.3);
        }

        .audio-control:hover {
            transform: scale(1.1);
            box-shadow: 0 0 25px rgba(255, 105, 180, 0.6);
        }

        .audio-control.playing {
            animation: spin 4s linear infinite;
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Marquee */
        .marquee-container {
            background: rgba(0, 0, 0, 0.5);
            border-top: 2px dashed var(--hot-pink);
            border-bottom: 2px dashed var(--hot-pink);
            padding: 5px 0;
            margin: 20px 0;
            overflow: hidden;
        }

        .marquee {
            white-space: nowrap;
            animation: marquee 20s linear infinite;
            color: var(--baby-blue);
            font-size: 1.1rem;
        }

        @keyframes marquee {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        /* Footer */
        .footer {
            text-align: center;
            margin-top: 40px;
            padding: 20px;
            border-top: 2px dotted rgba(255, 255, 255, 0.2);
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
        }

        .footer a {
            color: var(--hot-pink);
            text-decoration: none;
        }

        .footer a:hover {
            text-decoration: underline;
            text-shadow: 0 0 10px var(--hot-pink);
        }

        /* Responsive */
        @media (max-width: 600px) {
            .bunny-paw {
                transform: scale(0.8);
            }
            .header h1 {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>

    <!-- Audio Control -->
    <div class="audio-control" id="audioBtn" title="Toggle Lo-Fi Vibes">🔇</div>

    <!-- Secret Button -->
    <button class="secret-btn" id="secretBtn" title="?"></button>

    <!-- Dance Overlay -->
    <div class="dance-overlay" id="danceOverlay">
        <div class="dance-bunny">🐰</div>
        <div class="dance-text">BUNNY DANCE ACTIVATED</div>
        <div style="color: #fff; font-size: 0.7rem; margin-top: 20px;">click anywhere to escape</div>
    </div>

    <!-- Sparkles Container -->
    <div id="sparkles"></div>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="construction-tape">UNDER CONSTRUCTION FOREVER</div>
            <h1>☆ The Bunny Paw ☆<br>Fortune Teller</h1>
            <div class="subtitle">~* Internet Checkpoint *~</div>
            <div class="marquee-container">
                <div class="marquee">
                    ☆ Welcome to the checkpoint. Rest your paws here. ☆ You are safe. ☆ The bunny sees all. ☆ Take a fortune. ☆ Leave a message. ☆ Return when you need rest. ☆
                </div>
            </div>
        </div>

        <!-- The Paw -->
        <div class="paw-container">
            <div class="bunny-paw" id="bunnyPaw">
                <div class="toe toe-1" data-toe="1"></div>
                <div class="toe toe-2" data-toe="2"></div>
                <div class="toe toe-3" data-toe="3"></div>
                <div class="toe toe-4" data-toe="4"></div>
                <div class="paw-pad-main"></div>
            </div>
        </div>
        <div class="click-hint">☆ click a toe or the pad to receive your fate ☆</div>

        <!-- Fortune Display -->
        <div class="fortune-box">
            <div class="fortune-text" id="fortuneText">
                <span style="color: var(--chrome-dark)">The paw awaits your touch...</span>
                <span class="cursor-blink"></span>
            </div>
        </div>

        <!-- Visitor Counter -->
        <div class="visitor-counter">
            <span class="counter-label">YOU ARE VISITOR NUMBER</span>
            <div class="odometer" id="visitorCounter">0042069</div>
        </div>

        <!-- Guestbook -->
        <div class="chrome-panel">
            <div class="panel-title">📖 The Eternal Guestbook 📖</div>
            <div class="guestbook-feed" id="guestbookFeed"></div>
            <div class="guestbook-input">
                <input type="text" id="guestInput" placeholder="Leave your mark on the checkpoint..." maxlength="100">
                <button class="btn" id="guestSubmit">Sign</button>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>Made with 🐰 by a wanderer of the old web</p>
            <p>Best viewed in Netscape Navigator at 800x600</p>
            <p style="margin-top: 10px; font-size: 0.7rem;">
                <a href="#">Webring</a> :: 
                <a href="#">GeoCities</a> :: 
                <a href="#">Guestbook</a> :: 
                <a href="#">Email Me</a>
            </p>
        </div>
    </div>

    <script>
        // Fortunes Database
        const fortunes = [
            "You will find a loose grape in a place where no grapes should be.",
            "The next dog you see will have a secret opinion about your shoes.",
            "Beware the blue mailbox; it knows what you did last Tuesday.",
            "A pigeon has been keeping a dossier on your lunch habits.",
            "Your left sock is planning a solo career without you.",
            "The vending machine two blocks away is dreaming of you.",
            "You will sneeze exactly three times in the next 24 hours. Do not fight it.",
            "A forgotten password from 2007 holds the key to nothing important.",
            "The next time you blink, a sentient AI in Nebraska will do the same.",
            "Beware of Tuesdays. Not this one. A future one. You'll know.",
            "Your high school locker combination is now the WiFi password of a ghost.",
            "A cloud that looks like your childhood pet is watching you scroll.",
            "The fortune you seek is in another tab. Check your browser history.",
            "You will receive an email from a prince, but he only wants to be friends.",
            "The last Pringle in the can has been plotting against you since noon.",
            "Your future self just facepalmed at something you're about to do tomorrow.",
            "A raccoon has nominated you for an award you cannot claim.",
            "The number 7 is avoiding you today. Do not take it personally.",
            "Your refrigerator light has taken 4,327 photographs of you.",
            "A distant relative you have never met has your exact Spotify playlist.",
            "The next fortune cookie you open will be empty. This is not a bug.",
            "You are currently running on 23% nostalgia and 8% caffeine.",
            "A traffic cone in your city has achieved consciousness and chose peace.",
            "Your shadow has been submitting negative performance reviews about you.",
            "The \"ding\" of a microwave 3 miles away was actually for you.",
            "Your unused gym membership has gained sentience and feels abandoned.",
            "A sticker you placed in 2004 is still holding on. Believe in it.",
            "The next elevator you enter will smell faintly of 1998.",
            "Your plants are talking about you. The cactus is the ringleader.",
            "A CAPTCHA recently decided you were not human, but kept it to itself.",
            "The \"close door\" button in an elevator you used in 2019 finally worked.",
            "Your favorite pen ran away to join a circus. It is happier now.",
            "A shopping cart in a parking lot has been waiting for your return since June.",
            "The loading icon you are watching has been watching you back.",
            "Someone from a dream you forgot has filed a missing person report on you.",
            "Your old MySpace top 8 still thinks about you sometimes.",
            "The moon is in retrograde, but only for people who own more than 3 houseplants.",
            "A spider in your vicinity has written a polite review of your cleanliness.",
            "Your car keys have formed a union and are demanding better pockets.",
            "The \"reply all\" button you fear has been training for this moment.",
            "A pop-up ad from 2004 is still searching for a browser to call home."
        ];

        // Typewriter effect
        let typeTimeout;
        function typeFortune(text) {
            const fortuneEl = document.getElementById('fortuneText');
            clearTimeout(typeTimeout);
            fortuneEl.innerHTML = '<span class="cursor-blink"></span>';
            let i = 0;
            
            function type() {
                if (i < text.length) {
                    fortuneEl.innerHTML = text.substring(0, i + 1) + '<span class="cursor-blink"></span>';
                    i++;
                    typeTimeout = setTimeout(type, 30 + Math.random() * 50);
                } else {
                    fortuneEl.innerHTML = text + '<span class="cursor-blink"></span>';
                }
            }
            type();
        }

        // Fortune Logic
        function getFortune() {
            const fortune = fortunes[Math.floor(Math.random() * fortunes.length)];
            typeFortune(fortune);
            
            // Visual feedback
            const paw = document.getElementById('bunnyPaw');
            paw.style.transform = 'scale(0.9)';
            setTimeout(() => {
                paw.style.transform = '';
            }, 150);
        }

        document.getElementById('bunnyPaw').addEventListener('click', getFortune);
        document.querySelectorAll('.toe').forEach(toe => {
            toe.addEventListener('click', (e) => {
                e.stopPropagation();
                getFortune();
            });
        });

        // Guestbook Logic
        const prefixPool = [
            "Checkpoint:",
            "Resting my paws:",
            "Bunny says:",
            "Visitor log:",
            "Paw print:"
        ];

        const seededMessages = [
            { text: "just passing through on my way to geocities", time: "1998-04-12 02:34" },
            { text: "the grape prophecy came true. im scared.", time: "2003-11-05 14:22" },
            { text: "this is my third visit today. i cant leave.", time: "2024-06-17 09:15" },
            { text: "the paw knows. the paw always knows.", time: "2001-09-09 09:09" },
            { text: "resting my paws after a long day of net surfing", time: "2005-03-22 18:45" },
            { text: "beware the blue mailbox!!! it happened to me!!!", time: "2012-12-12 12:12" },
            { text: "i came for a fortune and stayed for the vibe", time: "2026-01-01 00:00" }
        ];

        function loadGuestbook() {
            const feed = document.getElementById('guestbookFeed');
            const stored = JSON.parse(localStorage.getItem('bunnyCheckpoint') || '[]');
            const allMessages = [...seededMessages, ...stored];
            
            feed.innerHTML = '';
            allMessages.slice().reverse().forEach(entry => {
                const prefix = prefixPool[Math.floor(Math.random() * prefixPool.length)];
                const div = document.createElement('div');
                div.className = 'guest-entry';
                div.innerHTML = `
                    <span class="guest-time">${entry.time}</span>
                    <span class="guest-prefix">${prefix}</span> ${entry.text}
                `;
                feed.appendChild(div);
            });
        }

        document.getElementById('guestSubmit').addEventListener('click', () => {
            const input = document.getElementById('guestInput');
            const text = input.value.trim();
            if (!text) return;
            
            const stored = JSON.parse(localStorage.getItem('bunnyCheckpoint') || '[]');
            const now = new Date();
            const timeStr = `${now.getFullYear()}-${String(now.getMonth()+1).padStart(2,'0')}-${String(now.getDate()).padStart(2,'0')} ${String(now.getHours()).padStart(2,'0')}:${String(now.getMinutes()).padStart(2,'0')}`;
            
            stored.push({ text, time: timeStr });
            if (stored.length > 50) stored.shift();
            localStorage.setItem('bunnyCheckpoint', JSON.stringify(stored));
            
            input.value = '';
            loadGuestbook();
        });

        document.getElementById('guestInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') document.getElementById('guestSubmit').click();
        });

        // Visitor Counter
        function initCounter() {
            const counter = document.getElementById('visitorCounter');
            let visits = parseInt(localStorage.getItem('bunnyVisits') || '42069');
            visits++;
            localStorage.setItem('bunnyVisits', visits.toString());
            
            // Animate to final number
            let display = 42069;
            const interval = setInterval(() => {
                display += Math.ceil((visits - display) / 10);
                if (display >= visits) {
                    display = visits;
                    clearInterval(interval);
                }
                counter.textContent = String(display).padStart(7, '0');
            }, 50);
        }

        // Secret Bunny Dance
        const secretBtn = document.getElementById('secretBtn');
        const danceOverlay = document.getElementById('danceOverlay');
        
        secretBtn.addEventListener('click', () => {
            danceOverlay.classList.add('active');
            playWeirdSound();
        });

        danceOverlay.addEventListener('click', () => {
            danceOverlay.classList.remove('active');
        });

        // Generative Audio System (Web Audio API)
        let audioCtx;
        let isPlaying = false;
        let audioInterval;

        const audioBtn = document.getElementById('audioBtn');

        function initAudio() {
            if (!audioCtx) {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            }
        }

        function playTone(freq, duration, type = 'sine', vol = 0.1) {
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.type = type;
            osc.frequency.value = freq;
            gain.gain.setValueAtTime(vol, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + duration);
            osc.connect(gain);
            gain.connect(audioCtx.destination);
            osc.start();
            osc.stop(audioCtx.currentTime + duration);
        }

        function playLoFiLoop() {
            // Simple generative lo-fi melody
            const scale = [220, 261.63, 293.66, 329.63, 349.23, 392.00, 440, 523.25];
            const bassScale = [110, 130.81, 146.83, 164.81];
            
            audioInterval = setInterval(() => {
                if (!isPlaying) return;
                
                // Random melody note
                if (Math.random() > 0.3) {
                    const note = scale[Math.floor(Math.random() * scale.length)];
                    playTone(note, 0.4 + Math.random() * 0.4, 'sine', 0.05);
                }
                
                // Random bass note
                if (Math.random() > 0.5) {
                    const bass = bassScale[Math.floor(Math.random() * bassScale.length)];
                    playTone(bass, 0.8, 'triangle', 0.08);
                }
                
                // Random hi-hat like noise
                if (Math.random() > 0.6) {
                    playTone(800 + Math.random() * 1200, 0.05, 'square', 0.02);
                }
            }, 250);
        }

        function playWeirdSound() {
            initAudio();
            // Chaotic bunny dance sound
            for (let i = 0; i < 10; i++) {
                setTimeout(() => {
                    const freq = 200 + Math.random() * 800;
                    playTone(freq, 0.2, 'sawtooth', 0.1);
                }, i * 100);
            }
        }

        audioBtn.addEventListener('click', () => {
            initAudio();
            isPlaying = !isPlaying;
            
            if (isPlaying) {
                audioBtn.textContent = '🎵';
                audioBtn.classList.add('playing');
                playLoFiLoop();
            } else {
                audioBtn.textContent = '🔇';
                audioBtn.classList.remove('playing');
                clearInterval(audioInterval);
            }
        });

        // Sparkle Generator
        function createSparkles() {
            const container = document.getElementById('sparkles');
            const symbols = ['✦', '✧', '⋆', '˚', '｡', '·', '✮', '✯'];
            
            setInterval(() => {
                const sparkle = document.createElement('div');
                sparkle.className = 'sparkle';
                sparkle.textContent = symbols[Math.floor(Math.random() * symbols.length)];
                sparkle.style.left = Math.random() * 100 + 'vw';
                sparkle.style.animationDuration = (5 + Math.random() * 10) + 's';
                sparkle.style.color = ['#ff69b4', '#00ffff', '#ccff00', '#ffffff'][Math.floor(Math.random() * 4)];
                container.appendChild(sparkle);
                
                setTimeout(() => sparkle.remove(), 15000);
            }, 300);
        }

        // Init
        loadGuestbook();
        initCounter();
        createSparkles();
    </script>
</body>
</html>
