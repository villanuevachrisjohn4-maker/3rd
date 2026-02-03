<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy 3rd Monthsary ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Handwritten Font -->
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@500;600&display=swap" rel="stylesheet">

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #ffdbe5;
  min-height: 100vh;
  overflow-x: hidden;
  font-family: 'Dancing Script', cursive;
}

/* CENTER */
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

/* ENVELOPE */
.envelope {
  width: 320px;
  height: 220px;
  position: relative;
  cursor: pointer;
  transition: opacity 1.2s ease;
}

/* Hide overflow so letter starts INSIDE */
.envelope-inner {
  position: absolute;
  inset: 0;
  overflow: hidden;
}

/* Envelope parts */
.envelope-back {
  position: absolute;
  inset: 0;
  background: #f4a7b9;
  border-radius: 16px;
  z-index: 1;
}

.envelope-front {
  position: absolute;
  inset: 0;
  background: #f7b7c8;
  clip-path: polygon(0 0, 100% 0, 50% 55%);
  z-index: 3;
}

.envelope-flap {
  position: absolute;
  inset: 0;
  background: #f09fb2;
  clip-path: polygon(0 0, 100% 0, 50% 60%);
  transform-origin: top;
  transition: transform 1s ease;
  z-index: 4;
}

.heart-seal {
  position: absolute;
  top: 48%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 26px;
  z-index: 5;
}

/* LETTER */
.letter-wrapper {
  position: absolute;
  left: 50%;
  top: 100%;
  transform: translate(-50%, 0);
  transition: transform 1.4s ease;
  z-index: 2;
}

.letter {
  width: 300px;
  max-height: 360px;
  padding: 28px 24px;
  background:
    linear-gradient(180deg, rgba(255,255,255,0.92), rgba(255,235,242,0.95)),
    repeating-linear-gradient(
      to bottom,
      rgba(0,0,0,0.03),
      rgba(0,0,0,0.03) 1px,
      transparent 1px,
      transparent 4px
    );
  border-radius: 18px;
  border: 2px solid #f2a7ba;
  box-shadow: 0 18px 35px rgba(231, 84, 128, 0.3);
  overflow-y: auto;
}

/* Scrollbar soft look */
.letter::-webkit-scrollbar {
  width: 6px;
}
.letter::-webkit-scrollbar-thumb {
  background: #e48aa2;
  border-radius: 10px;
}

/* Title */
.letter h1 {
  text-align: center;
  color: #d94a73;
  margin-bottom: 18px;
  font-size: 26px;
}

/* Text */
.letter p {
  font-size: 18px;
  line-height: 2;
  color: #6b2d3e;
  margin-bottom: 18px;
}

/* OPEN STATES */
.envelope.open .envelope-flap {
  transform: rotateX(-180deg);
}

.envelope.open .letter-wrapper {
  transform: translate(-50%, -340px);
}

.envelope.fade {
  opacity: 0;
  pointer-events: none;
}

/* Floating hearts */
#hearts span {
  position: fixed;
  bottom: -20px;
  animation: float 6s linear forwards;
}

@keyframes float {
  to { transform: translateY(-120vh); opacity: 0; }
}
</style>
</head>

<body>

<div class="container">
  <div class="envelope" id="envelope">

    <div class="envelope-inner">
      <div class="letter-wrapper">
        <div class="letter">
          <h1>💗 Monthsary</h1>

          <p>Three months may not seem like a long time, but to me, it already feels like we’ve built something really special.</p>

          <p>In just a short time, you’ve become someone I look forward to every day someone who makes my ordinary moments feel brighter and my heavy days feel lighter.</p>

          <p>Thank you for being patient with me, for understanding me, and for choosing me even when things aren’t perfect.</p>

          <p>If this is just the beginning, then I can’t wait to see how much more we’ll grow together. I choose you now and forever. ❤️</p>
        </div>
      </div>
    </div>

    <div class="envelope-back"></div>
    <div class="envelope-front"></div>
    <div class="envelope-flap"></div>
    <div class="heart-seal">❤️</div>

  </div>
</div>

<div id="hearts"></div>

<script>
const envelope = document.getElementById("envelope");
let opened = false;

envelope.addEventListener("click", () => {
  if (opened) return;
  opened = true;

  envelope.classList.add("open");

  // Fade envelope after opening
  setTimeout(() => {
    envelope.classList.add("fade");
  }, 1600);
});

/* Floating hearts */
setInterval(() => {
  const h = document.createElement("span");
  h.innerHTML = "❤️";
  h.style.left = Math.random() * 100 + "vw";
  h.style.fontSize = Math.random() * 10 + 14 + "px";
  document.getElementById("hearts").appendChild(h);
  setTimeout(() => h.remove(), 6000);
}, 700);
</script>

</body>
</html>
