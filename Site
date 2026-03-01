<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>A Beautiful World for Ayomide</title>

<style>
body{
  margin:0;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:linear-gradient(135deg,#fbd3e9,#bbf7d0);
  font-family:Arial,sans-serif;
}

.bubble{
  width:330px;
  background:radial-gradient(circle at top,#ffffff,#ffd6e8);
  border-radius:20px;
  padding:25px;
  text-align:center;
  box-shadow:0 0 40px rgba(255,255,255,0.8);
}

h2{color:#ff4f7b;}

button{
  margin:6px;
  padding:10px 16px;
  border:none;
  border-radius:18px;
  font-size:15px;
  cursor:pointer;
}
.yes{background:#ff4f7b;color:white;}
.no{background:#ccc;}
.back{background:#aaa;color:white;}
.hidden{display:none;}

#buttons{margin-top:15px;}
</style>
</head>

<body>

<audio id="music" loop>
  <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_9c7a3c3b31.mp3" type="audio/mpeg">
</audio>

<div class="bubble">
  <div id="content"></div>

  <div id="buttons" class="hidden">
    <button class="yes" onclick="chooseYes()">YES</button>
    <button class="no" onclick="chooseNo()">NO</button>
    <button class="back" onclick="goBack()">BACK</button>
  </div>
</div>

<script>
const content = document.getElementById("content");
const buttons = document.getElementById("buttons");
const music = document.getElementById("music");

let step = 0;
let history = [];

/* ---------- RENDER ---------- */
function render(){
  buttons.classList.remove("hidden");

  if(step === 0){
    buttons.classList.add("hidden");
    content.innerHTML = `
      <h2>🧚‍♀️✨</h2>
      <p>Welcome to a beautiful world for Ayomide 💖</p>
      <button class="yes" onclick="start()">Enter the World</button><br><br>
      <button class="yes" onclick="music.play()">Start Music 🎵</button>
    `;
  }

  else if(step === 1){
    content.innerHTML = `
      <h2>Ayomide 💕</h2>
      <p>Do you want us to be something special together?</p>
    `;
  }

  /* YES PATH */
  else if(step === 2){
    content.innerHTML = `<h2>🥹</h2><p>Wow… for real?</p>`;
  }
  else if(step === 3){
    content.innerHTML = `<h2>💖</h2><p>I will be the best person in the world for you.</p>`;
  }
  else if(step === 4){
    music.pause();
    content.innerHTML = `
      <h2>🥹💖</h2>
      <p>
        Thank you…  
        I may not be rich, but I promise to love you,  
        lift us up together, and take care of you  
        with all I have.
      </p>
      <p><b>📸 Please screenshot this and send it to me.</b></p>
    `;
  }

  /* NO PATH */
  else if(step === 5){
    content.innerHTML = `<h2>😔</h2><p>Wow… I really thought you liked me.</p>`;
  }
  else if(step === 6){
    content.innerHTML = `<h2>💔</h2><p>I put my heart into this… are you really sure?</p>`;
  }
  else if(step === 7){
    music.pause();
    content.innerHTML = `
      <h2>😞</h2>
      <p>
        I can’t change your choice…  
        but I really hoped you wouldn’t choose this.
      </p>
      <p><b>📸 Please screenshot this and send it to me.</b></p>
    `;
  }
}

/* ---------- ACTIONS ---------- */
function start(){
  history.push(step);
  step = 1;
  render();
}

function chooseYes(){
  history.push(step);
  if(step === 1) step = 2;
  else if(step === 2) step = 3;
  else if(step === 3) step = 4;
  else if(step >= 5) step = 2; // YES after NO
  render();
}

function chooseNo(){
  history.push(step);
  if(step === 1) step = 5;
  else if(step === 5) step = 6;
  else if(step === 6) step = 7;
  else if(step <= 4) step = 5; // NO after YES
  render();
}

function goBack(){
  if(history.length > 0){
    step = history.pop();
    render();
  }
}

/* ---------- INIT ---------- */
render();
</script>

</body>
</html>
