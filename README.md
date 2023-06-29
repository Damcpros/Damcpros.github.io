<!DOCTYPE html>
<html>
<head>
  <title>Simple Chat System</title>
  <style>
    #chat-container {
      border: 1px solid #ccc;
      padding: 10px;
      width: 300px;
      height: 300px;
      overflow-y: scroll;
    }
    #message-input {
      width: 200px;
    }
  </style>
  <script>
    document.addEventListener("DOMContentLoaded", function() {
      const chatContainer = document.getElementById("chat-container");
      const messageInput = document.getElementById("message-input");
      const sendButton = document.getElementById("send-button");

      sendButton.addEventListener("click", function() {
        const message = messageInput.value;
        if (message !== "") {
          appendMessage("You", message);
          messageInput.value = "";
        }
      });

      function appendMessage(sender, message) {
        const messageElement = document.createElement("p");
        messageElement.innerHTML = `<strong>${sender}: </strong>${message}`;
        chatContainer.appendChild(messageElement);
        chatContainer.scrollTop = chatContainer.scrollHeight;
      }
    });
  </script>
</head>
<body>
  <h1>Simple Chat System</h1>

  <div id="chat-container"></div>

  <input type="text" id="message-input" placeholder="Type your message..." />
  <button id="send-button">Send</button>
</body>
</html>
