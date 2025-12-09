<html>
<head>
  <title>Exam Doubt Clarification Portal</title>
  <style>

    body{
      background:blue;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .chat-container {
      width: 400px;
      background:white ;
      border-radius: 8px;
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }
    .chat-header {
      background:orange;
      color: white;
      padding: 10px;
      text-align: center;
      font-weight: bold;
    }
    .chat-box {
      flex: 1;
      padding: 10px;
      overflow-y: auto;
    }
    .message {
      margin: 8px 0;
      padding: 8px 12px;
      border-radius: 6px;
      max-width: 80%;
    }
    .student {
      background: white;
      align-self: flex-end;
    }
    .teacher {
      background:white;
      align-self: flex-start;
    }
    .chat-input {
      display: flex;
      border-top: 1px solid #ddd;
    }
    .chat-input input {
      flex: 1;
      padding: 10px;
      border: none;
      outline: none;
    }
    .chat-input button {
      background: #4CAF50;
      color: white;
      border: none;
      padding: 10px 15px;
      cursor: pointer;
    }
    .chat-input button:hover {
      background: #45a049;
    }
  </style>
</head>
<body>
  <div class="chat-container">
    <div class="chat-header">Exam Doubt Clarification Portal</div>
    <div class="chat-box" id="chatBox"></div>
    <div class="chat-input">
      <input type="text" id="userInput" placeholder="Type your doubt...">
      <button onclick="sendMessage()">Send</button>
    </div>
  </div>

  <script>
    function sendMessage() {
      const input = document.getElementById("userInput");
      const chatBox = document.getElementById("chatBox");
      const message = input.value.trim();

      if (message !== "") {
        
        const studentMsg = document.createElement("div");
        studentMsg.className = "message student";
        studentMsg.textContent = message;
        chatBox.appendChild(studentMsg);

        
        const teacherMsg = document.createElement("div");
        teacherMsg.className = "message teacher";
        teacherMsg.textContent = "Thanks for your doubt! A teacher will clarify soon.";
        chatBox.appendChild(teacherMsg);

        
        chatBox.scrollTop = chatBox.scrollHeight;

        input.value = "";
      }
    }
  </script>
</body>
</html>
