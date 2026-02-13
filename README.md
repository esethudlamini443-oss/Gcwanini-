<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine 💘</title>

<style>
body {
  margin: 0;
  padding: 30px;
  font-family: "Segoe UI", Arial, sans-serif;
  text-align: center;
  background: linear-gradient(135deg, #f7c1df, #d9c9f2);
  overflow: hidden;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  background: radial-gradient(circle, rgba(200,200,200,0.15), transparent);
  pointer-events: none;
}

h1 { color: #2f2f2f; }
p { color: #3a2d4f; font-weight: 500; }

button {
  padding: 15px 32px;
  font-size: 18px;
  border-radius: 30px;
  border: none;
  cursor: pointer;
  margin: 20px;
}

#yesBtn {
  background: linear-gradient(to right, #ff9acb, #caa7f5);
  color: #2b2b2b;
}

#noBtn {
  background-color: #f5f5f5;
  color: #6a3c88;
  position: absolute;
}

@keyframes shake {
  0% { transform: translateX(0); }
  25% { transform: translateX(-5px); }
  50% { transform: translateX(5px); }
  75% { transform: translateX(-5px); }
  100% { transform: translateX(0); }
}

#tapScreen {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.35);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.3em;
  z-index: 10;
}
</style>
</head>

<body>

<div id="tapScreen" onclick="startMusic()">Tap anywhere to begin 💕</div>

<!-- 🎵 EMBEDDED MUSIC -->
<audio id="bgMusic" loop>
  <source src="https://drive.google.com/uc?export=download&id=11V95CRiR2bh7kkIx43LyG9by6ghmFrgS" type="audio/mpeg">
</audio>

<h1>Hey My Love 💕</h1>

<h1>Will you be my Valentine? 💘</h1>

<button id="yesBtn" onclick="yesClicked()">YES 💖</button>
<button id="noBtn">NO 🙄</button>

<script>
function startMusic() {
  document.getElementById("bgMusic").play();
  document.getElementById("tapScreen").style.display = "none";
}

const noBtn = document.getElementById("noBtn");
let hoverCount = 0;

noBtn.addEventListener("mouseover", () => {
  hoverCount++;
  noBtn.style.animation = "shake 0.3s";
  setTimeout(() => noBtn.style.animation = "", 300);

  noBtn.style.left = Math.random() * (window.innerWidth - 150) + "px";
  noBtn.style.top = Math.random() * (window.innerHeight - 100) + "px";

  if (hoverCount >= 5) {
    noBtn.innerHTML = "YES 💖";
    noBtn.onclick = yesClicked;
  }
});

function yesClicked() {
  document.body.innerHTML = `
    <h1>CONGRATULATIONS 🎉💖</h1>
    <p>You are officially my Valentine 🥰</p>
    <p style="font-size:1.4em; color:#4b2c63;">
     My heart ❤️. I gotta be honest with you this is my first valentine ngikwi relationship and I'm kinda nervous 🥹. I'm so happy to be experiencing so many firsts with you 🥰 and I pray and hope that you be my last too 🙏❤️. I wanted to tell you how much I appreciate you, your presence, your kindness, your handsomeness and your sweetness (in both the figurative and literal way 😉🤫). You are such a blessing and I want to celebrate our love every second of everyday until forever ♾️. You came into my life unexpectedly and you took over in my heart ❤️. You became my source of happiness, peace and laughter. You are literally my best friend (... second best friend 🥹 but don't worry you are my one and only life partner). You took me to a place where I didn't think I'd ever be in again. You made me bubbly and lively again and for that I'm so very thankful to you ❤️. Your hugs are like a blanket of warmth and you truly feel like home 😩😍. Ngyabonga for loving me Gcwanini, ngyabonga for making me happy again and most importantly thank you for being here whenever I need you. I promise to give you my outmost best even in tough times 🥹. I love you more than you'll ever know 🥹❤️. Have the happiest valentine ❤️ ( ungakhohlwa ukungbeke kuNkulunkulu at church 🙏❤️). YAMKELA, choosing you is my favourite decision.<br>
      Today. Tomorrow. Always 💕
    </p>
  `;
}
</script>

</body>
</html>
