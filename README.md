# -<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Моя валентинка для тебя!</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #ffe4e1; /* Нежно-розовый фон */
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #8b0000; /* Темно-красный текст */
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
            text-align: center;
            overflow: hidden; /* Чтобы кнопка не убегала за пределы */
        }

        h1 {
            font-size: 2.5em;
            margin-bottom: 40px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        .buttons-container {
            display: flex;
            gap: 30px;
            margin-top: 20px;
            position: relative; /* Для позиционирования кнопки 'Нет' */
        }

        button {
            padding: 15px 30px;
            font-size: 1.5em;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            position: relative;
        }

        #yesBtn {
            background-color: #ff69b4; /* Ярко-розовый */
            color: white;
        }

        #yesBtn:hover {
            background-color: #ff1493; /* Более темный розовый */
            transform: translateY(-3px);
            box-shadow: 0 6px 10px rgba(0,0,0,0.15);
        }

        #noBtn {
            background-color: #ffffff; /* Белый */
            color: #ff69b4;
            border: 2px solid #ff69b4;
        }

        #noBtn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 10px rgba(0,0,0,0.15);
        }

        .result-content {
            display: none; /* Скрыто по умолчанию */
            margin-top: 50px;
            animation: fadeIn 1s ease-in-out;
        }

        .result-content img {
            max-width: 80%;
            height: auto;
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 8px 15px rgba(0,0,0,0.2);
        }

        .result-content p {
            font-size: 2em;
            font-weight: bold;
            color: #d62828; /* Яркий красный */
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Адаптивность для мобильных устройств */
        @media (max-width: 600px) {
            h1 {
                font-size: 1.8em;
                margin-bottom: 30px;
            }
            button {
                padding: 12px 25px;
                font-size: 1.2em;
            }
            .buttons-container {
                flex-direction: column; /* Кнопки друг под другом на мобильных */
                gap: 15px;
            }
            .result-content p {
                font-size: 1.5em;
            }
        }
    </style>
</head>
<body>

    <div id="main-content">
        <h1>Будешь моей валентинкой?</h1>
        <div class="buttons-container">
            <button id="yesBtn">Да ❤️</button>
            <button id="noBtn">Нет</button>
        </div>
    </div>

    <div id="result" class="result-content">
        <img src="ВАША_ССЫЛКА_НА_ФОТО.jpg" alt="Ваша совместная фотография">
        <p>Я знала! 🥰</p>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const mainContent = document.getElementById('main-content');
        const resultContent = document.getElementById('result');

        // Функция для перемещения кнопки "Нет"
        noBtn.addEventListener('mouseover', () => {
            const maxX = window.innerWidth - noBtn.clientWidth;
            const maxY = window.innerHeight - noBtn.clientHeight;

            const newX = Math.random() * maxX;
            const newY = Math.random() * maxY;

            noBtn.style.position = 'absolute'; // Делаем кнопку абсолютно позиционированной
            noBtn.style.left = `${newX}px`;
            noBtn.style.top = `${newY}px`;
        });

        // При нажатии на "Да"
        yesBtn.addEventListener('click', () => {
            mainContent.style.display = 'none'; // Скрываем вопрос и кнопки
            resultContent.style.display = 'block'; // Показываем результат
        });

        // Задаем начальную позицию для кнопки "Нет" (чтобы она не была в углу)
        window.addEventListener('load', () => {
            noBtn.style.position = 'relative'; // Сбросим, если до этого был absolute
            noBtn.style.left = 'auto';
            noBtn.style.top = 'auto';
        });

    </script>

</body>
</html>
