<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Анонимный Чат</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #007bff;
            color: #fff;
            text-align: center;
            padding: 1em;
        }

        main {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        #chat-messages {
            list-style: none;
            padding: 0;
            margin: 0;
            max-height: 300px;
            overflow-y: auto;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 10px;
        }

        #input-container {
            margin-top: 20px;
        }

        input[type="text"] {
            width: 80%;
            padding: 8px;
            margin-right: 5px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        input[type="submit"] {
            background-color: #4caf50;
            color: #fff;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        input[type="submit"]:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <header>
        <h1>Анонимный Чат</h1>
    </header>

    <main>
        <ul id="chat-messages"></ul>

        <div id="input-container">
            <input type="text" id="message" placeholder="Введите сообщение" autocomplete="off">
            <input type="submit" value="Отправить" onclick="sendMessage()">
        </div>
    </main>

    <script>
        function sendMessage() {
            var messageInput = document.getElementById('message');
            var message = messageInput.value.trim();

            if (message !== "") {
                var chatMessages = document.getElementById('chat-messages');
                var listItem = document.createElement('li');
                listItem.textContent = message;
                chatMessages.appendChild(listItem);

                // Очищаем поле ввода
                messageInput.value = '';

                // Прокручиваем вниз, чтобы видеть последнее сообщение
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
        }
    </script>
</body>
</html>
