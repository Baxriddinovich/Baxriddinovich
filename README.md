## Hi there 👋
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacker Style GitHub README</title>
    <style>
        body {
            background: #0d1117;
            color: #00ff00;
            font-family: 'Courier New', Courier, monospace;
            text-align: center;
            margin: 0;
            padding: 20px;
            overflow-x: hidden;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            border: 2px solid #00ff00;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
        }
        h1 {
            font-size: 2.5em;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 10px #00ff00;
        }
        p {
            font-size: 1.2em;
            line-height: 1.6;
        }
        .terminal {
            background: #000;
            padding: 20px;
            border-radius: 5px;
            text-align: left;
            white-space: pre-wrap;
            font-size: 1em;
            margin: 20px 0;
        }
        .blink {
            animation: blink 1s step-end infinite;
        }
        @keyframes blink {
            50% { opacity: 0; }
        }
        .social-links a {
            color: #00ff00;
            text-decoration: none;
            margin: 0 10px;
            font-size: 1.1em;
        }
        .social-links a:hover {
            text-shadow: 0 0 10px #00ff00;
        }
        .matrix {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }
    </style>
</head>
<body>
    <canvas id="matrix" class="matrix"></canvas>
    <div class="container">
        <h1>👾 [Your GitHub Username]</h1>
        <p>Welcome to my digital lair! I'm a coder, hacker, and tech enthusiast.</p>
        <div class="terminal">
            $ whoami
            > [Your Name]
            $ skills
            > JavaScript | Python | HTML | CSS | Cybersecurity
            $ status
            > Hacking the mainframe... <span class="blink">_</span>
        </div>
        <div class="social-links">
            <a href="https://x.com/yourusername" target="_blank">X Profile</a> |
            <a href="https://linkedin.com/in/yourusername" target="_blank">LinkedIn</a> |
            <a href="mailto:your.email@example.com">Email</a>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');

        canvas.height = window.innerHeight;
        canvas.width = window.innerWidth;

        const chars = '01abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ@#$%^&*';
        const fontSize = 14;
        const columns = canvas.width / fontSize;
        const drops = [];

        for (let x = 0; x < columns; x++) {
            drops[x] = 1;
        }

        function draw() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = '#00ff00';
            ctx.font = fontSize + 'px monospace';

            for (let i = 0; i < drops.length; i++) {
                const text = chars.charAt(Math.floor(Math.random() * chars.length));
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);

                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(draw, 33);

        window.addEventListener('resize', () => {
            canvas.height = window.innerHeight;
            canvas.width = window.innerWidth;
        });
    </script>
</body>
</html>
