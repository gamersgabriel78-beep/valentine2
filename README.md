<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine 💖</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0;
      text-align: center;
    }

    .container {
      background: white;
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
      max-width: 400px;
      width: 90%;
    }

    h1 {
      color: #ff4d6d;
    }

    button {
      padding: 12px 25px;
      margin: 15px;
      font-size: 16px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      transition: 0.3s;
    }

    #yesBtn {
      background-color: #ff4d6d;
      color: white;
    }

    #yesBtn:hover {
      background-color: #e63950;
    }

    #noBtn {
      background-color: #ccc;
      position: relative;
    }

    .party {
      display: none;
    }

    .party img {
      width: 100%;
      border-radius: 15px;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1 id="question">You want to be my Valentine? 💘</h1>

    <div id="buttons">
      <button id="yesBtn" onclick="yesClicked()">YES 💖</button>
      <button id="noBtn" onclick="noClicked()">NO 🙄</button>
    </div>

    <div class="party" id="party">
      <h1>Uyyyyyy!!! 🎉💃🕺</h1>
      <p>I knew you’d say yes my asawa 💕</p>
      <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExYzZxdjRiYThqcm80NXUxZHJmbTcxbG45Y3piajdhbHo5bmR5Yzd2MSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/i21tixUQEE7TEqwmYa/giphy.gif">
      <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExb3drM2J2cXE4ZjZqOHRhbDRwdXJqcGdtM3AydHFtYmUzdHZhNWczciZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/bpTL6wXRuMQpMIVduB/giphy.gif">
    </div>
  </div>

  <script>
    let noCount = 0;

    function yesClicked() {
      document.getElementById("question").style.display = "none";
      document.getElementById("buttons").style.display = "none";
      document.getElementById("party").style.display = "block";
    }

    function noClicked() {
      noCount++;
      const question = document.getElementById("question");

      const messages = [
        "Are you suuuure babyy? 🥺",
        "why u want to say no huh? 😳",
        "What if I ask nicely? 💕",
        "comeeee onnnnnn click yes mi amor 😘",
        "its okay baby but i always love you u know huh 🥹",
        "Last chance 👀💖"
      ];

      question.innerText =
        messages[Math.min(noCount - 1, messages.length - 1)];

      const noBtn = document.getElementById("noBtn");
      const yesBtn = document.getElementById("yesBtn");

      // Move NO randomly
      noBtn.style.position = "absolute";
      noBtn.style.top = Math.random() * 80 + "%";
      noBtn.style.left = Math.random() * 80 + "%";

      // NO gets smaller 😈
      const noScale = Math.max(0.4, 1 - noCount * 0.15);
      noBtn.style.transform = `scale(${noScale})`;

      // YES gets bigger 💖
      const yesScale = Math.min(2.5, 1 + noCount * 0.2);
      yesBtn.style.transform = `scale(${yesScale})`;
    }
  </script>

</body>
</html>



