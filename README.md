<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clicker Game</title>
    <style>
        /* CSS стили */
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }

        .container {
            text-align: center;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            margin: 0 0 20px;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Clicker Game</h1>
        <p>Clicks: <span id="clickCount">0</span></p>
        <button id="clickButton">Click Me!</button>
    </div>
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
