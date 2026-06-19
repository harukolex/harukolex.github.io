<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title> :) </title>

<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;600;700&display=swap" rel="stylesheet">

<style>
body {
  margin: 0;
  height: 100vh;
  background: #000;
  font-family: "Noto Serif TC", serif;

  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  color: white;
}

.hidden { display: none; }

.card {
  text-align: center;
  animation: fadeIn 0.6s ease;
}

.banner {
  max-width: 95vw;
  max-height: 70vh;

  width: auto;
  height: auto;

  filter: drop-shadow(0 15px 30px rgba(0,0,0,0.6));
}
.heart-column {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);

  display: flex !important;
  flex-direction: column !important;  /* ⭐直列核心 */
  align-items: center;
  gap: 15px;

  color: #ff8fb1;
  font-size: 65px;
  font-weight: 700;
  line-height: 1;

  text-shadow: 0 0 12px rgba(255,143,177,0.35);
}

.heart-left {
  left: 50px;
}

.heart-right {
  right: 50px;
}
/* ⭐動畫：先出第一行 */
.line-small {
  opacity: 0;
  transform: translateY(10px);
  animation: fadeUp 0.8s ease forwards;
  font-size: 25px
}

/* ⭐動畫：第二行延遲2秒出現 */
.line-big {
  opacity: 0;
  transform: translateY(10px);
  animation: fadeUp 0.8s ease forwards;
  animation-delay: 1s;

  font-size: 32px;
  font-weight: 700;
  margin: 6px 0 20px;
}

/* ⭐動畫本體 */
@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 2;
    transform: translateY(0);
  }
}
.pink-text {
  color: #ff8fb1;
  font-size: 22px;
  font-weight: 700;
}

.invite-text {
  color: #ff8fb1;
  font-size: 28px;
  font-weight: 700;
  margin: 18px 0 24px;

  opacity: 0;
  transform: translateY(10px);
  animation: fadeUp 0.8s ease forwards;
  animation-delay: 0.1s;
}

.final-main {
  color: #ff8fb1;
  font-size: 48px;
  font-weight: 700;
  text-shadow: 0 0 12px rgba(255,143,177,0.35);
  margin-bottom: 10px;
}

.final-sub {
  color: rgba(255,255,255,0.6);
  font-size: 16px;
  font-weight: 700;
}

/* buttons */
.buttons { margin-top: 20px; }

button {
  border: none;
  padding: 12px 26px;
  margin: 10px;
  border-radius: 999px;
  font-size: 16px;
  cursor: pointer;
  transition: 0.2s;
  font-family: "Noto Serif TC", serif;

  box-sizing: border-box; /* ⭐防止變形 */
}

button:hover {
  transform: none;
}
  
.happy-btn{
  opacity: 0;
  background: #ffd9e6;
  color: #444;
  transform: translateY(10px);
  animation: fadeUp 0.8s ease forwards;
  animation-delay: 1s;
}
  
.sad-btn {
  opacity: 0;
  background: #dfe7f0;
  color: #444;
  transform: translateY(10px);
  animation: fadeUp 0.8s ease forwards;
  animation-delay: 1s;
}
.yes {
  background: #ffe86a;
  color: #ff7ca8;
  font-weight: 700;
  font-size: 22px;
  padding: 18px 42px;

  opacity: 0;
  transform: translateY(10px);
  animation: fadeUp 0.8s ease forwards;
  animation-delay: 1s;
}

.no {
  background: #444;
  color: white;
  font-size: 13px;
  padding: 8px 16px;

  position: fixed;
  right: 30px;
  bottom: 30px;

  z-index: 999;
  width: 120px;
  height: 36px;

  display: flex;
  align-items: center;
  justify-content: center;

  white-space: nowrap;
}
  opacity: 0;
  transform: translateY(10px);
  transition: left 0.08s linear, top 0.08s linear;
  pointer-events: none; /* ⭐避免還沒出現就能互動 */
}
.no.show {
  animation: fadeUp 0.2s ease forwards;
  pointer-events: auto;
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div class="card" id="page1">
 <div class="heart-column heart-left">
    <div>❤</div>
    <div>❤</div>
    <div>❤</div>
  </div>

  <div class="heart-column heart-right">
    <div>❤</div>
    <div>❤</div>
    <div>❤</div>
  </div>
  <img id="img1" class="banner" src="img-normal.png">

  <div class="line-small">ねね、あのさ～～～</div>
  <div class="line-big">今日どうだったの♪？</div>

  <div class="buttons">
    <button class="happy-btn" onmouseover="setHappy()" onclick="next()">
      ヤバすごい一日だったよ❤
    </button>

    <button class="sad-btn" onmouseover="setSad()" onclick="next()">
      あまりよくない...😞🥺
    </button>
  </div>
</div>

<!-- PAGE 2 -->
<div class="card hidden" id="page2">

  <img id="img2" class="banner" src="img-page2-happy.gif">

  <div class="invite-text">
    じゃ... 晚點要不要...ちょっと...那個一下
  </div>
 <div class="heart-column heart-left">
    <div>❤</div>
    <div>❤</div>
    <div>❤</div>
  </div>

  <div class="heart-column heart-right">
    <div>❤</div>
    <div>❤</div>
    <div>❤</div>
  </div>
  <div class="buttons">

    <button class="yes" onmouseover="page2Happy()" onclick="yes()">
      もちろんいいよ♪👍🏻
    </button>

   <button class="no" id="noBtn" onmouseover="moveAway(event)">
      嫌だ！
    </button>

  </div>

  <p style="opacity:0.6;font-size:14px;">
    断ってみろよ＼＼٩(๑`^´๑)۶／／
  </p>
</div>

<!-- PAGE 3 -->
<div class="card hidden" id="page3">

  <div class="heart-column heart-left">
    <div>❤</div>
    <div>❤</div>
    <div>❤</div>
  </div>

  <div class="heart-column heart-right">
    <div>❤</div>
    <div>❤</div>
    <div>❤</div>
  </div>

  <img class="banner" src="img-final.png">

  <div class="final-main">やったー！！！</div>
  <div class="final-sub">（Lineでいつ空いてるか教えてね）</div>

</div>

<script>
let noTextIndex = 0;
/* images */
const imgHappy = "img-happy.png";
const imgSad = "img-sad.png";
const imgPage2Happy = "img-page2-happy.gif";
const imgPage2Angry = "img-page2-angry.png";

/* page1 */
function setHappy() {
  document.getElementById("img1").src = imgHappy;
}

function setSad() {
  document.getElementById("img1").src = imgSad;
}

/* page2 */
function page2Happy() {
  document.getElementById("img2").src = imgPage2Happy;
}

function page2Angry() {
  document.getElementById("img2").src = imgPage2Angry;
}

/* navigation */
function next() {
  document.getElementById("page1").classList.add("hidden");
  document.getElementById("page2").classList.remove("hidden");

  const noBtn = document.getElementById("noBtn");
  const invite = document.querySelector(".invite-text");

  // 先確保 noBtn 是隱藏狀態
  noBtn.classList.remove("show");

  // ⭐等 invite 動畫跑完，再 + 0.8s
  setTimeout(() => {
    noBtn.classList.add("show");
  }, 1300); 
  // 你可以調這個數字：
  // invite animation delay(0.5s) + 動畫時間 + 0.8s
}

function yes() {
  document.getElementById("page2").classList.add("hidden");
  document.getElementById("page3").classList.remove("hidden");
}

/* NO button logic */
const noBtn = document.getElementById("noBtn");

function resetNoBtn() {
  noBtn.style.left = "auto";
  noBtn.style.top = "auto";

  noBtn.style.right = "30px";
  noBtn.style.bottom = "30px";

  noBtn.style.position = "fixed";
  noBtn.style.opacity = "1";
  noBtn.style.pointerEvents = "auto";

  noBtn.innerText = "嫌だ！";
}

/* hover escape */
function moveAway(e) {

  const noBtn = document.getElementById("noBtn");
  page2Angry();

  const rect = noBtn.getBoundingClientRect();

  const mouseX = e.clientX;
  const mouseY = e.clientY;

  const btnW = rect.width;
  const btnH = rect.height;

  const padding = 30;

  // 🧠 1. 算逃離方向
  let dx = rect.left + btnW / 3 - mouseX;
  let dy = rect.top + btnH / 3 - mouseY;

  const dist = Math.sqrt(dx * dx + dy * dy) || 1;

  const speed = 230;

  let moveX = (dx / dist) * speed;
  let moveY = (dy / dist) * speed;

  // 🧠 2. 新位置（用 viewport，而不是累加）
  let newX = rect.left + moveX;
  let newY = rect.top + moveY;

  const maxX = window.innerWidth - btnW - padding;
  const maxY = window.innerHeight - btnH - padding;

  // 🧠 3. 超界直接「重抽位置」（關鍵改這裡）
  if (newX < padding || newX > maxX || newY < padding || newY > maxY) {
    newX = padding + Math.random() * (maxX - padding);
    newY = padding + Math.random() * (maxY - padding);
  }

  noBtn.style.position = "fixed";
  noBtn.style.left = newX + "px";
  noBtn.style.top = newY + "px";

  // 👉 這行確保不會被 CSS transition 卡住
  noBtn.style.transition = "left 0.08s linear, top 0.08s linear";

  const texts = [
    "再給你一次機會",
    "もう一回考えろよ！",
    "バカ？",
    "本当？",
    "不准欸",
    "沒愛了"
  ];

  noBtn.innerText = texts[noTextIndex];
noTextIndex = (noTextIndex + 1) % texts.length;
}
  </script> 
  </body> 
</html>
