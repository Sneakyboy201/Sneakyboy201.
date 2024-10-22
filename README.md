# Sneakyboy201. <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Game Room - Multiplayer Lobby</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            width: 80%;
            max-width: 1200px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 20px;
            padding: 20px;
        }
        .game-section {
            display: flex;
            flex-direction: column;
        }
        .game-frame {
            flex: 1;
            background-color: #ddd;
            border-radius: 10px;
            overflow: hidden;
        }
        iframe {
            width: 100%;
            height: 400px;
            border: none;
        }
        .chat-section {
            display: flex;
            flex-direction: column;
            background-color: #f9f9f9;
            border-radius: 10px;
            padding: 10px;
            height: 100%;
        }
        .chat-header {
            text-align: center;
            background-color: #4285F4;
            color: white;
            padding: 10px;
            border-radius: 5px;
        }
        .chat-box {
            flex: 1;
            background-color: #e6e6e6;
            margin: 10px 0;
            border-radius: 5px;
            padding: 10px;
            overflow-y: scroll;
        }
        .chat-message {
            margin-bottom: 10px;
            padding: 8px;
            background-color: #fff;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        .chat-input {
            display: flex;
        }
        .chat-input input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px 0 0 5px;
        }
        .chat-input button {
            padding: 10px;
            background-color: #4285F4;
            color: white;
            border: none;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
        }
        .chat-input button:hover {
            background-color: #3072C4;
        }
        .player-list {
            background-color: #f9f9f9;
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
        }
        .player-list h2 {
            text-align: center;
            margin-bottom: 10px;
        }
        .player {
            padding: 10px;
            background-color: #e6e6e6;
            margin-bottom: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="game-section">
            <h1 style="text-align: center;">Multiplayer Game Room</h1>
            <div class="game-frame">
                <!-- Embed Game or Interactive Content Here -->
                <iframe src="https://examplegame.com" title="Game"></iframe>
            </div>
        </div>

        <div class="chat-section">
            <div class="chat-header">
                <h2>Chat</h2>
            </div>
            <div class="chat-box" id="chat-box">
                <div class="chat-message">
                    <strong>Player1:</strong> Hello!
                </div>
                <div class="chat-message">
                    <strong>Player2:</strong> Hi, ready to play?
                </div>
            </div>
            <div class="chat-input">
                <input type="text" placeholder="Type your message here..." id="chat-input">
                <button onclick="sendMessage()">Send</button>
            </div>
            <div class="player-list">
                <h2>Players</h2>
                <div class="player">Player1</div>
                <div class="player">Player2</div>
                <div class="player">Player3</div>
            </div>
        </div>
    </div>

    <script>
        function sendMessage() {
            var input = document.getElementById('chat-input');
            var message = input.value.trim();
            if (message) {
                var chatBox = document.getElementById('chat-box');
                var newMessage = document.createElement('div');
                newMessage.className = 'chat-message';
                newMessage.innerHTML = '<strong>You:</strong> ' + message;
                chatBox.appendChild(newMessage);
                chatBox.scrollTop = chatBox.scrollHeight; // Scroll to the bottom
                input.value = ''; // Clear the input
            }
        }
    </script>
</body>
</html>
