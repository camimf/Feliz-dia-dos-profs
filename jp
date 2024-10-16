<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crash - Quebre as Caixas!</title>
    <style>
        body {
            background-image: url('https://imgur.com/L6snppv.png'); /* Imagem de fundo */
            background-size: cover;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            color: white;
            text-align: center;
        }
        #game-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-bottom: 20px;
        }
        .box {
            width: 100px;
            height: 100px;
            margin: 10px;
            background-image: url('https://imgur.com/7U6GqvQ.png'); /* Imagem da caixa */
            background-size: cover;
            cursor: pointer;
        }
        #win-message, #final-message {
            display: none;
        }
        #crash, #crash-end {
            width: 100px;
            display: none;
        }
        #final-image {
            display: none;
        }
    </style>
</head>
<body>

    <h1>Crash - Quebre as Caixas!</h1>
    <button id="start-button">Iniciar Jogo</button>
    <div id="timer">Tempo: <span id="time-left">30</span> segundos</div>
    <div id="game-container"></div>
    <div id="win-message">Você venceu!</div>

    <img id="crash" src="https://imgur.com/C52LthZ.png" alt="Crash Bandicoot">
    <img id="crash-end" src="https://imgur.com/C52LthZ.png" alt="Crash Bandicoot Final">

    <div id="final-message">Feliz dia dos professores, você é incrível em tudo o que se propõe a fazer, eu amo você!</div>
    <img id="final-image" src="https://imgur.com/LapGpL7.png" alt="Imagem Final">

    <script>
        const gameContainer = document.getElementById('game-container');
        const winMessage = document.getElementById('win-message');
        const crashImage = document.getElementById('crash');
        const crashEndImage = document.getElementById('crash-end');
        const finalMessage = document.getElementById('final-message');
        const finalImage = document.getElementById('final-image');
        const timeLeftDisplay = document.getElementById('time-left');
        let boxCount = 12;
        let timeLeft = 30;
        let timer;
        let boxes = [];

        function createBoxes() {
            gameContainer.innerHTML = ""; // Limpa o contêiner de caixas
            for (let i = 0; i < boxCount; i++) {
                const box = document.createElement('div');
                box.classList.add('box');
                box.addEventListener('click', breakBox);
                boxes.push(box);
                gameContainer.appendChild(box);
            }
        }

        function breakBox(event) {
            event.target.remove();
            boxCount--;
            checkWin();
        }

        function checkWin() {
            if (boxCount === 0) {
                clearInterval(timer);
                winMessage.style.display = 'block';
                crashEndImage.style.display = 'block';
                finalMessage.style.display = 'block';
                finalImage.style.display = 'block';
            }
        }

        function startTimer() {
            timer = setInterval(() => {
                timeLeft--;
                timeLeftDisplay.textContent = timeLeft;

                if (timeLeft <= 0) {
                    clearInterval(timer);
                    winMessage.textContent = "Tempo esgotado! Você perdeu!";
                    winMessage.style.display = 'block';
                    crashEndImage.style.display = 'block';
                    finalMessage.style.display = 'block';
                    finalImage.style.display = 'block';
                }
            }, 1000);
        }

        document.getElementById('start-button').addEventListener('click', function() {
            createBoxes();
            startTimer();
            this.style.display = 'none'; // Esconde o botão após o clique
        });
    </script>

</body>
</html>
