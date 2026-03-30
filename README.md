
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>An ủi Tuấn Anh</title>

<style>
body {
    background: linear-gradient(to right, #ffd6e7, #cceeff);
    font-family: Arial;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    background: white;
    width: 500px;
    padding: 30px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 15px 40px rgba(0,0,0,0.2);
    position: relative;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    margin: 10px;
    border-radius: 10px;
    border: none;
    background-color: #ff99cc;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.05);
    background-color: #ff66aa;
}

img {
    width: 250px;
    margin-top: 15px;
    border-radius: 15px;
    border: 4px solid white;
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    transition: 0.3s;
}

img:hover {
    transform: scale(1.05);
    box-shadow: 0 15px 35px rgba(0,0,0,0.3);
}

#noBtn {
    position: absolute;
}

#extraText {
    display: none;
    font-size: 18px;
    margin-top: 10px;
    color: #ff6699;
}
</style>

</head>
<body>

<audio id="music" loop>
    <source src="nhac.mp3" type="audio/mpeg">
</audio>

<div class="container">
    <h2 id="question">Bạn Tuấn Anh có cảm thấy mình đẹp trai nhưng bị khùng không (°ロ°)?</h2>

    <!-- FIX LỖI Ở ĐÂY -->
    <img id="image" src="tuananh.jpg">

    <br>

    <div id="buttons">
        <button onclick="start()">Có</button>
        <button id="noBtn" onmouseover="moveButton()">Không</button>
    </div>

    <p id="extraText"></p>
</div>

<script>
function moveButton() {
    let btn = document.getElementById("noBtn");
    btn.style.top = Math.random() * 300 + "px";
    btn.style.left = Math.random() * 300 + "px";
}

function start() {
    document.getElementById("music").play();

    document.getElementById("question").innerText =
    "Không phải m ko đủ tốt, chỉ là người kia không biết trân trọng thôi 😎";
    document.getElementById("image").src = "meme.gif";

    document.getElementById("buttons").innerHTML =
    '<button onclick="nextStep()">T hiểu rồi</button>' +
    '<button onclick="alert(\'Có ý kiến cũng phải theo ý t wa ha ha ha\')">Có ý kiến gì báo 115</button>';
}

function nextStep() {
    document.getElementById("question").innerText =
    "Có người vẫn quan tâm m đó, buồn thì buồn, nhưng đừng buồn quá lâu nha, ăn uốn đúng giờ vào, ngủ sớm nữa 😁";
    document.getElementById("image").src = "cute.jpg";

    document.getElementById("buttons").innerHTML = '';

    setTimeout(() => {
        document.getElementById("extraText").style.display = "block";
        document.getElementById("extraText").innerText = "Từ từ cải thiện nha 💖";
    }, 1500);
}
</script>

</body>
</html>
