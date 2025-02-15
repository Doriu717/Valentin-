<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Поздравление с 14 февраля</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: black;
            font-family: Arial, sans-serif;
            color: white;
            overflow: hidden;
            flex-direction: column;
            position: relative;
        }

        /* Стиль для формы ввода имени */
        .input-container {
            text-align: center;
            z-index: 2;
            opacity: 1;
            transition: opacity 1s ease-out;
        }

        input {
            padding: 10px;
            font-size: 18px;
            text-align: center;
            border: none;
            border-radius: 5px;
            outline: none;
            width: 200px;
        }

        button {
            margin-top: 10px;
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            background-color: red;
            color: white;
            cursor: pointer;
        }

        /* Стиль для текста поздравления */
        .message-container {
            display: none;
            text-align: center;
            z-index: 1;
            position: absolute;
        }

        .message {
            font-size: 30px;
            font-weight: bold;
            opacity: 0;
            transition: opacity 1s ease-in-out;
            margin-bottom: 20px;
        }

        /* Стиль для имени */
        .name {
            font-size: 36px;
            font-weight: bold;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }

        /* Эффект дождя */
        .rain {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        .drop {
            position: absolute;
            width: 2px;
            height: 15px;
            background: rgba(255, 255, 255, 0.7);
            animation: rain 0.5s linear infinite;
        }
        @keyframes rain {
            to {
                transform: translateY(100vh);
            }
        }

        /* Эффект звезд */
        .stars {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 0;
        }
        .star {
            position: absolute;
            width: 3px;
            height: 3px;
            background: white;
            border-radius: 50%;
            animation: twinkle 2s infinite alternate;
        }
        @keyframes twinkle {
            0% { opacity: 0.5; transform: scale(1); }
            100% { opacity: 1; transform: scale(1.5); }
        }

        /* Эффект для смайликов ❤️ */
        .hearts {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 0;
        }

        .heart {
            position: absolute;
            font-size: 50px;
            animation: beat 1s infinite;
        }

        @keyframes beat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }

    </style>
</head>
<body>

    <!-- Форма ввода имени -->
    <div class="input-container" id="inputContainer">
        <h2>Введите ваше имя</h2>
        <input type="text" id="nameInput" placeholder="Ваше имя">
        <button onclick="submitName()">Далее</button>
    </div>

    <!-- Поздравление -->
    <div class="message-container" id="messageContainer">
        <div class="message" id="message1">С 14 февраля!</div>
        <div class="message" id="message2">Желаю тебе счастья и любви!</div>
        <div class="message" id="message3">Ты — мой лучший друг, моя опора и поддержка.</div>
        <div class="message" id="message4">С каждым днем я все больше осознаю, как мне повезло быть с тобой!</div>
        <div class="message" id="message5">Ты — невероятный человек, и я благодарен за то, что ты есть в моей жизни.</div>
        <div class="name" id="userName"></div>
    </div>

    <!-- Дождь -->
    <div class="rain" id="rain"></div>

    <!-- Звезды -->
    <div class="stars" id="stars"></div>

    <!-- Смайлики -->
    <div class="hearts" id="hearts"></div>

    <!-- Звук биения сердца -->
    <audio id="heartbeatSound" loop>
        <source src="https://www.soundjay.com/button/beep-07.wav" type="audio/wav">
    </audio>

    <script>
        // Функция для обработки ввода имени и показа поздравления
        function submitName() {
            let name = document.getElementById("nameInput").value.trim();
            if (name === "") {
                alert("Пожалуйста, введите имя!");
                return;
            }

            // Плавное исчезновение формы ввода
            document.getElementById("inputContainer").style.opacity = "0";
            setTimeout(() => {
                document.getElementById("inputContainer").style.display = "none";
            }, 1000); // Задержка для плавного исчезновения

            // Показать поздравление
            document.getElementById("messageContainer").style.display = "block";

            // Показать первое сообщение с плавным появлением
            setTimeout(() => {
                document.getElementById("message1").style.opacity = "1";
            }, 1000);

            // Показать второе сообщение через 2 секунды с плавным появлением
            setTimeout(() => {
                document.getElementById("message2").style.opacity = "1";
            }, 3000);

            // Показать третье сообщение через 4 секунды с плавным появлением
            setTimeout(() => {
                document.getElementById("message3").style.opacity = "1";
            }, 5000);

            // Показать четвертое сообщение через 6 секунд с плавным появлением
            setTimeout(() => {
                document.getElementById("message4").style.opacity = "1";
            }, 7000);

            // Показать пятое сообщение через 8 секунд с плавным появлением
            setTimeout(() => {
                document.getElementById("message5").style.opacity = "1";
            }, 9000);

            // Показать имя с персонализированным поздравлением через 12 секунд
            setTimeout(() => {
                let personalizedMessage = "";
                if (name.toLowerCase() === "лина") {
                    personalizedMessage = name + " — любимая сестра!";
                } else if (name.toLowerCase() === "даниел" || name.toLowerCase() === "daniel") {
                    personalizedMessage = name + " — любимый бро!";
                } else if (name.toLowerCase() === "дина") {
                    personalizedMessage = name + " — самая лучшая принцесса!";
                } else {
                    personalizedMessage = name + " — замечательный человек!";
                }
                document.getElementById("userName").textContent = personalizedMessage;
                document.getElementById("userName").style.opacity = "1";
            }, 12000);

            // Запуск дождя и звезд
            createRain();
            createStars();
            createHearts();

            // Включить звук биения сердца
            document.getElementById("heartbeatSound").play();
        }

        // Функция для создания дождя
        function createRain() {
            const rainContainer = document.getElementById("rain");
            for (let i = 0; i < 100; i++) {
                let drop = document.createElement("div");
                drop.classList.add("drop");
                drop.style.left = Math.random() * 100 + "vw";
                drop.style.animationDuration = (Math.random() * 2 + 2) + "s"; // скорость дождя
                rainContainer.appendChild(drop);
            }
        }

        // Функция для создания звезд
        function createStars() {
            const starsContainer = document.getElementById("stars");
            for (let i = 0; i < 50; i++) {
                let star = document.createElement("div");
                star.classList.add("star");
                star.style.left = Math.random() * 100 + "vw";
                star.style.top = Math.random() * 100 + "vh";
                star.style.animationDuration = (Math.random() * 2 + 1) + "s"; // скорость мигания звезд
                starsContainer.appendChild(star);
            }
        }

        // Функция для создания смайликов ❤️
        function createHearts() {
            const heartsContainer = document.getElementById("hearts");
            for (let i = 0; i < 30; i++) {
                let heart = document.createElement("div");
                heart.classList.add("heart");
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.top = Math.random() * 100 + "vh";
                heart.textContent = "❤️";
                heartsContainer.appendChild(heart);
            }
        }
    </script>

</body>
</html>
