# Chat-Application3
Chat Application3
<!DOCTYPE html>
<html>
<head>
  <title>Simple Chat App</title>
  <style>
    /* Inline CSS for simplicity */
    body {
      font-family: Arial, sans-serif;
    }
    #chat-box {
      width: 300px;
      height: 400px;
      border: 1px solid #ccc;
      overflow-y: scroll;
      padding: 10px;
    }
    #input-box {
      width: 100%;
      padding: 5px;
    }
    #send-button {
      padding: 5px 10px;
      margin-top: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div id="chat-box"></div>
  <input type="text" id="input-box" placeholder="Type a message...">
  <button id="send-button">Send</button>

  <script>
    // JavaScript for handling the chat functionality
    document.getElementById('send-button').addEventListener('click', function() {
      sendMessage();
    });

    document.getElementById('input-box').addEventListener('keypress', function(e) {
      if (e.key === 'Enter') {
        sendMessage();
      }
    });

    function sendMessage() {
      var messageInput = document.getElementById('input-box');
      var message = messageInput.value;
      if (message.trim() !== '') {
        appendMessage('You: ' + message);
        messageInput.value = '';
        // You can replace the below line with actual logic to send the message to a server or another user
        simulateReply();
      }
    }

    function simulateReply() {
      setTimeout(function() {
        var reply = 'Bot: Hello! This is a bot reply.';
        appendMessage(reply);
      }, 500);
    }

    function appendMessage(message) {
      var chatBox = document.getElementById('chat-box');
      var messageElement = document.createElement('div');
      messageElement.textContent = message;
      chatBox.appendChild(messageElement);
      chatBox.scrollTop = chatBox.scrollHeight;
    }
  </script>
</body>
</html>
