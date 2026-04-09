<!DOCTYPE html>  
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Question 😊</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        font-family: Arial, sans-serif;
        background: linear-gradient(to right, #ff9a9e, #fad0c4);
        overflow: hidden;
    }

    h1 {
        font-size: 40px;
        color: #fff;
    }

    .buttons {
        margin-top: 20px;
    }

    button {
        padding: 12px 25px;
        font-size: 18px;
        border: none;
        border-radius: 25px;
        margin: 10px;
        cursor: pointer;
        position: relative;
    }

    #yesBtn {
        background-color: #fff;
        color: #ff4d6d;
    }

    #noBtn {
        background-color: #ff4d6d;
        color: white;
        position: absolute;
    }

    .float {
        position: absolute;
        font-size: 30px;
        animation: floatUp 4s linear forwards;
    }

    .message {
        position: absolute;
        font-size: 40px;
        color: #fff;
        font-weight: bold;
        text-shadow: 2px 2px 10px rgba(0,0,0,0.3);
        animation: floatMessage 5s ease forwards;
    }

    @keyframes floatUp {
        0% { transform: translateY(0); opacity: 1; }
        100% { transform: translateY(-800px); opacity: 0; }
    }

    @keyframes floatMessage {
        0% { transform: translateY(0) rotate(0deg); opacity: 1; }
        50% { transform: translateY(-300px) rotate(10deg); }
        100% { transform: translateY(-600px) rotate(-5deg); opacity: 0; }
    }
</style>
</head>

<body>

<h1>Do you love me? 😊</h1>

<div class="buttons">
    <button id="yesBtn" onclick="celebrate()">Yes 💖</button>
    <button id="noBtn" onmouseover="moveNo()">No 😜</button>
</div>

<script>
function celebrate() {
    // floating hearts and roses
    for (let i = 0; i < 25; i++) {
        let el = document.createElement("div");
        el.className = "float";
        el.innerHTML = Math.random() > 0.5 ? "❤️" : "🌹";
        el.style.left = Math.random() * window.innerWidth + "px";
        el.style.bottom = "0px";
        el.style.fontSize = (20 + Math.random() * 30) + "px";
        el.style.animationDuration = (3 + Math.random() * 2) + "s";
        document.body.appendChild(el);
        setTimeout(() => el.remove(), 4000);
    }

    // floating "I love you too baby 🌹" message
    let msg = document.createElement("div");
    msg.className = "message";
    msg.innerHTML = "I love you too baby 🌹";
    msg.style.left = (window.innerWidth / 2 - 150) + "px"; // center
    msg.style.bottom = "0px";
    document.body.appendChild(msg);
    setTimeout(() => msg.remove(), 5000);
}

function moveNo() {
    let noBtn = document.getElementById("noBtn");
    let x = Math.random() * (window.innerWidth - 100);
    let y = Math.random() * (window.innerHeight - 100);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
}
</script>

</body>
</html>
