<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<title>Happy 3rd Monthsary ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0" />

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Georgia, serif;
}

body {
  background: linear-gradient(135deg, #ffd1dc, #ffe6eb);
  min-height: 100vh;
  overflow: hidden;
}

/* CENTER */
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

/* ENVELOPE */
.envelope {
  width: 320px;
  height: 220px;
  position: relative;
  cursor: pointer;
  perspective: 1000px;
}

.envelope-back {
  position: absolute;
  inset: 0;
  background: #f4a7b9;
  border-radius: 8px;
  z-index: 1;
}

.envelope-front {
  position: absolute;
  inset: 0;
  background: #f7b7c8;
  clip-path: polygon(0 0, 100% 0, 50% 55%);
  z-index: 4;
  transition: opacity 0.6s ease;
}

.envelope-flap {
  position: absolute;
  inset: 0;
  background: #f09fb2;
  clip-path: polygon(0 0, 100% 0, 50% 60%);
  transform-origin: top;
  transition: transform 1s ease;
  z-index: 5;
}

.heart-seal {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 26px;
  z-index: 6;
}

/* CARD */
.card-wrapper {
  position: absolute;
  width: 100%;
  top: 0;
  left: 0;
  transform: translateY(60px);
  transition: transform 1.2s ease;
  z-index: 2;
}

.card {
  background: white;
  padding: 22px;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0,0,0,0.15);
}

.card h1 {
  font-size: 26px;
}

.card h1 span {
  font-size: 20px;
  color: #e75480;
}

.card-body {
  margin-top: 12px;
  font-size: 14px;
  line-height: 1.7;
  text-align: left;
  min-height: 240px;
}

/* OPEN STATE */
.envelope.open .envelope-flap {
  transform: rotateX(-180deg);
}

.envelope.open .card-wrapper {
  transform: translateY(-260px);
}

.envelope.open .envelope-front {
  opacity: 0;
}

/* CURSOR */
.type-cursor::after {
  content: "|";
  animation: blink 1s infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}

/* HEARTS */
#hearts span {
  position: fixed;
  bottom: -20px;
  animation: float 6s linear forwards;
}

@keyframes float {
  from { transform: translateY(0); opacity: 1; }
  to { transform: translateY(-120vh); opacity: 0; }
}

/* SPARKLES */
#sparkles span {
  position: fixed;
  width: 6px;
  height: 6px;
  background: white;
  border-radius: 50%;
  opacity: 0.8;
  animation: sparkle 2.5s linear forwards;
}

@keyframes sparkle {
  0% { transform: scale(0); opacity: 1; }
  100% { transform: scale(1.5) translateY(-120px); opacity: 0; }
}
</style>
</head>

<body>

<audio id="bg-music" loop>
  <source src="music.mp3" type="audio/mpeg">
</audio>

<div class="container">
  <div class="envelope" id="envelope">
    <div class="envelope-back"></div>

    <div class="card-wrapper">
      <div class="card">
        <h1>3rd<br><span>Monthsary</span></h1>
        <div class="card-body" id="typed-text" data-text="
Three months may not seem like a long time, but to me, it already feels like we’ve built something really special.

In just a short time, you’ve become someone I look forward to every day—someone who makes my ordinary moments feel brighter and my heavy days feel lighter.

Thank you for being patient with me, for understanding me, and for choosing me even when things aren’t perfect.

If this is just the beginning, then I can’t wait to see how much more we’ll grow together. I choose you now and forever. ❤️
"></div>
      </div>
    </div>

    <div class="envelope-front"></div>
    <div class="envelope-flap"></div>
    <div class="heart-seal">❤️</div>
  </div>
</div>

<div id="hearts"></div>
<div id="sparkles"></div>

<script>
const envelope = document.getElementById("envelope");
const music = document.getElementById("bg-m
