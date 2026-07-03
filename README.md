<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Good Morning My Love ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    height:100vh;
    background:linear-gradient(135deg,#ffd1dc,#ff9a9e);
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
}

/* First Page */
#welcomePage{
    text-align:center;
    background:white;
    padding:40px;
    border-radius:25px;
    box-shadow:0 10px 30px rgba(0,0,0,0.2);
}

#welcomePage h1{
    color:#ff4d6d;
    margin-bottom:25px;
}

.btn{
    border:none;
    border-radius:30px;
    color:white;
    cursor:pointer;
    margin:10px;
    transition:0.3s;
}

#yesBtn{
    background:#ff4d6d;
    padding:12px 30px;
    font-size:18px;
}

#noBtn{
    background:#999;
    padding:12px 30px;
    font-size:18px;
}

.btn:hover{
    transform:scale(1.1);
}

/* Main Page */
#mainPage{
    display:none;
}

.card{
    background:white;
    padding:35px;
    border-radius:25px;
    text-align:center;
    width:350px;
    box-shadow:0 10px 30px rgba(0,0,0,0.2);
    z-index:2;
}

.card h1{
    color:#ff4d6d;
    margin-bottom:15px;
}

.card p{
    color:#555;
    line-height:1.6;
}

.loveBtn{
    background:#ff4d6d;
    color:white;
    border:none;
    padding:12px 24px;
    border-radius:30px;
    cursor:pointer;
    margin-top:15px;
    transition:0.3s;
}

.loveBtn:hover{
    transform:scale(1.1);
}

#message{
    display:none;
    margin-top:20px;
    color:#ff4d6d;
    font-weight:bold;
    line-height:1.8;
}

.heart{
    position:absolute;
    color:red;
    animation:float 8s linear infinite;
}

@keyframes float{
    from{
        transform:translateY(100vh);
        opacity:1;
    }
    to{
        transform:translateY(-100px);
        opacity:0;
    }
}
</style>
</head>

<body>

<!-- First Page -->
<div id="welcomePage">
    <h1>🥰 Did You Wake Up My Love?</h1>

    <button id="yesBtn" class="btn" onclick="openMorningPage()">
        Yes ❤️
    </button>

    <button id="noBtn" class="btn" onclick="clickNo()">
        No 😴
    </button>
</div>

<!-- Main Page -->
<div id="mainPage">
    <div class="card">
        <h1>🌞 Good Morning My Love ❤️</h1>

        <p>
            Every sunrise reminds me how lucky I am to have you.
            I hope today brings you happiness, peace, and countless smiles.
        </p>

        <button class="loveBtn" onclick="showLove()">
            💌 Open My Message
        </button>

        <div id="message">
            You are the first thought on my mind every morning and
            the sweetest reason behind my smile.<br><br>

            I know sometimes I make your blood boil, make you angry,
            sad, and feel all kinds of emotions. I'm truly sorry for
            putting you through those annoying moments.<br><br>

            But believe me, I REALLY LOVE YOU WITH ALL MY HEART. ❤️<br><br>

            I LOVE YOU SARA!! ❤️❤️❤️✨
        </div>
    </div>
</div>

<script>
let noClicks = 0;
let yesSize = 18;
let noSize = 18;

function clickNo(){
    noClicks++;

    yesSize += 8;
    noSize -= 3;

    document.getElementById("yesBtn").style.fontSize = yesSize + "px";
    document.getElementById("noBtn").style.fontSize =
        Math.max(noSize, 8) + "px";

    if(noClicks === 1){
        document.getElementById("noBtn").innerHTML =
        "Still Sleeping? 😴";
    }

    if(noClicks === 2){
        document.getElementById("noBtn").innerHTML =
        "Really? 🥺";
    }

    if(noClicks === 3){
        document.getElementById("noBtn").innerHTML =
        "Are You Sure? ❤️";
    }

    if(noClicks >= 4){
        document.getElementById("noBtn").style.display = "none";
    }
}

function openMorningPage(){
    document.getElementById("welcomePage").style.display = "none";
    document.getElementById("mainPage").style.display = "block";
}

function showLove(){
    document.getElementById("message").style.display = "block";

    for(let i=0;i<20;i++){
        let heart = document.createElement("div");
        heart.innerHTML = "❤️";
        heart.className = "heart";

        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = (20 + Math.random() * 25) + "px";
        heart.style.animationDuration =
        (4 + Math.random() * 4) + "s";

        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 8000);
    }
}
</script>

</body>
</html>
