<!DOCTYPE html>  
<html lang="ro">  
<head>  
<meta charset="UTF-8" />  
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
<title>Pentru bita ❤️</title>  
  
<style>  
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@500;700&display=swap');  
  
html, body {  
  margin: 0;  
  padding: 0;  
  height: 100%;  
  font-family: 'Quicksand', sans-serif;  
  background: black;  
  overflow: hidden;  
  color: white;  
}  
  
.stars {  
  position: fixed;  
  width: 100%;  
  height: 100%;  
  background: url("https://i.imgur.com/9QZ7R5D.png") repeat;  
  animation: moveStars 60s linear infinite;  
  z-index: -1;  
}  
  
@keyframes moveStars {  
  from {background-position: 0 0;}  
  to {background-position: -10000px 5000px;}  
}  
  
.screen {  
  display: none;  
  height: 100%;  
  width: 100%;  
  text-align: center;  
  padding: 40px 20px;  
  box-sizing: border-box;  
}  
  
.screen.active {  
  display: flex;  
  flex-direction: column;  
  justify-content: center;  
  align-items: center;  
}  
  
h1 {  
  font-size: 2.4em;  
  margin-bottom: 30px;  
}  
  
button {  
  padding: 14px 26px;  
  font-size: 1.1em;  
  border-radius: 30px;  
  border: none;  
  cursor: pointer;  
  margin: 10px;  
  transition: all 0.3s ease;  
}  
  
.btn-next {  
  background: #ff7eb3;  
  color: white;  
}  
  
.btn-yes {  
  background: #ff4d6d;  
  color: white;  
}  
  
.btn-no {  
  background: #555;  
  color: white;  
}  
  
.fireworks {  
  position: fixed;  
  inset: 0;  
  background: url("https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif") center/cover no-repeat;  
  display: none;  
  z-index: 10;  
}  
  
.final img {  
  max-width: 80%;  
  border-radius: 20px;  
  margin-top: 20px;  
  box-shadow: 0 0 20px rgba(255,255,255,0.6);  
}  
  
.final h1 {  
  font-size: 2.2em;  
}  
</style>  
</head>  
  
<body>  
  
<div class="stars"></div>  
  
<div class="screen active" id="s1">  
  <h1>Pentru bita ❤️</h1>  
  <button class="btn-next" onclick="next(1)">Continuă</button>  
</div>  
  
<div class="screen" id="s2">  
  <h1>Oare ce voiam să zic.. că am uitat</h1>  
  <button class="btn-next" onclick="next(2)">Continuă o dată</button>  
</div>  
  
<div class="screen" id="s3">  
  <h1>Do you want to be my valentine?</h1>  
  <div>  
    <button class="btn-yes" id="yesBtn" onclick="yes()">efectiv da</button>  
    <button class="btn-no" onclick="no()">nu.</button>  
  </div>  
</div>  
  
<div class="screen final" id="s4">  
  <h1>Te iubesc 🐥utica</h1>  
  <img src="poza-noastra.jpg" alt="Noi doi">  
</div>  
  
<div class="fireworks" id="fireworks"></div>  
  
<audio id="music" src="muzica-romantica.mp3"></audio>  
  
<script>  
let yesScale = 1;  
  
function next(n) {  
  document.getElementById("s" + n).classList.remove("active");  
  document.getElementById("s" + (n + 1)).classList.add("active");  
}  
  
function no() {  
  yesScale += 0.3;  
  const yesBtn = document.getElementById("yesBtn");  
  yesBtn.style.transform = `scale(${yesScale})`;  
  
  if (yesScale >= 3) {  
    document.querySelector(".btn-no").style.display = "none";  
  }  
}  
  
function yes() {  
  document.getElementById("s3").classList.remove("active");  
  document.getElementById("s4").classList.add("active");  
  
  document.getElementById("fireworks").style.display = "block";  
  
  const music = document.getElementById("music");  
  music.volume = 0.6;  
  music.play();  
}  
</script>  
  
</body>  
</html>  
