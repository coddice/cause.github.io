<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clicker Game</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

        body {
            font-family: 'Roboto', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            background: linear-gradient(270deg, #ff9a9e, #fad0c4);
            background-size: 600% 600%;
            animation: gradientAnimation 10s ease infinite;
        }

        @keyframes gradientAnimation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.8);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
        }

        h1 {
            margin: 0 0 20px;
            color: #333;
        }

        p {
            font-size: 1.5em;
            margin: 20px 0;
            color: #555;
        }

        button {
            padding: 15px 30px;
            font-size: 1.2em;
            font-weight: bold;
            color: #fff;
            background: #ff6f61;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: background 0.3s;
        }

        button:hover {
            background: #ff3b2d;
        }

        .gradient-box {
            position: absolute;
            width: 200px;
            height: 200px;
            border-radius: 20px;
            animation: colorChange 5s ease infinite;
        }

        .box1 {
            top: 20px;
            left: 20px;
            background: linear-gradient(45deg, #ff6f61, #ff3b2d);
            animation-delay: 0s;
        }

        .box2 {
            top: 20px;
            right: 20px;
            background: linear-gradient(45deg, #6a82fb, #fc5c7d);
            animation-delay: 1s;
        }

        .box3 {
            bottom: 20px;
            left: 20px;
            background: linear-gradient(45deg, #3ab8ea, #00d2ff);
            animation-delay: 2s;
        }

        .box4 {
            bottom: 20px;
            right: 20px;
            background: linear-gradient(45deg, #a8e063, #56ab2f);
            animation-delay: 3s;
        }

        @keyframes colorChange {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Clicker Game</h1>
        <p>Clicks: <span id="clickCount">0</span></p>
        <button id="clickButton">Click Me!</button>
    </div>
    <div class="gradient-box box1"></div>
    <div class="gradient-box box2"></div>
    <div class="gradient-box box3"></div>
    <div class="gradient-box box4"></div>

    <script>
        // JavaScript код
        let clickCount = parseInt(localStorage.getItem('clickCount')) || 0;
        document.getElementById('clickCount').textContent = clickCount;

        document.getElementById('clickButton').addEventListener('click', () => {
            clickCount++;
            document.getElementById('clickCount').textContent = clickCount;
            localStorage.setItem('clickCount', clickCount);
        });
    </script>
</body>
</html>
