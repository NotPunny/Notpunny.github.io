# Notpunny.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Click the Button Game</title>
    <style>
        /* Basic Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 20px;
            background-color: #f4f4f4;
        }

        h1 {
            font-size: 24px;
            margin-bottom: 20px;
        }

        #game-container {
            width: 100%;
            height: 70vh; /* Adjust height for mobile screens */
            position: relative;
            margin: 0 auto;
        }

        button {
            position: absolute;
            padding: 20px 30px;
            font-size: 20px;
            cursor: pointer;
            border-radius: 8px;
            background-color: #4CAF50;
            color: white;
            border: none;
            outline: none;
            transition: transform 0.2s ease-in-out;
        }

        #score {
            font-size: 22px;
            margin-top: 20px;
        }

        /* Media Queries for Mobile */
        @media (max-width: 600px) {
            button {
                font-size: 18px;
                padding: 15px 20px;
            }

            #score {
                font-size: 20px;
            }

            h1 {
                font-size: 20px;
            }

            #game-container {
                height: 60vh; /* Slightly smaller on mobile */
            }
        }
    </style>
</head>
<body>
    <h1>Click the Button Game!</h1>
    <div id="game-container">
        <button id="gameButton">Click Me!</button>
    </div>
    <p id="score">Score: 0</p>

    <script>
        let score = 0;
        const gameButton = document.getElementById("gameButton");
        const scoreDisplay = document.getElementById("score");
        const gameContainer = document.getElementById("game-container");

        // Function to move the button to a random position within the game container
        function moveButton() {
            const maxX = gameContainer.clientWidth - gameButton.clientWidth;
            const maxY = gameContainer.clientHeight - gameButton.clientHeight;
            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);

            gameButton.style.left = randomX + "px";
            gameButton.style.top = randomY + "px";
        }

        // Increase score when button is clicked
        gameButton.addEventListener("click", () => {
            score++;
            scoreDisplay.textContent = `Score: ${score}`;
            moveButton();
        });

        // Initially position the button
        moveButton();
    </script>
</body>
</html>
