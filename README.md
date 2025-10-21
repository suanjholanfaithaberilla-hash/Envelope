<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Envelope Click Story</title>
<link href="https://fonts.googleapis.com/css2?family=Patrick+Hand&display=swap" rel="stylesheet">
<style>
  body {
    margin: 0;
    background: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
    font-family: 'Patrick Hand', cursive;
  }

  .scene {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.8s ease;
  }

  .scene.active {
    opacity: 1;
    pointer-events: auto;
    z-index: 10;
  }

  svg {
    max-width: 90vw;
    max-height: 90vh;
  }

  .heart { fill: pink; stroke: black; stroke-width: 3; }
  .heart-fill { fill: #ff93c2; stroke: black; stroke-width: 6; }

  .hl-pink {
    background: #ffd9e8;
    padding: 4px 10px;
    border-radius: 12px;
  }
  .underline-blue {
    position: relative;
    display: inline-block;
    padding-bottom: 3px;
  }
  .underline-blue::after {
    content: "";
    position: absolute;
    left: 0; right: 0; bottom: 0;
    height: 4px;
    background: #aee3ff;
    border-radius: 4px;
  }
  .note-text {
    font-size: 28px;
    line-height: 1.1;
    text-align: left;
    color: #111;
  }

  .click-hint {
    position: absolute;
    bottom: 20px;
    font-size: 18px;
    color: #777;
    animation: blink 1.2s infinite;
  }

  @keyframes blink {
    0%, 50%, 100% { opacity: 1; }
    25%, 75% { opacity: 0.3; }
  }
</style>
</head>
<body>

<div class="scene active" id="scene1">
  <svg viewBox="0 0 200 150" xmlns="http://www.w3.org/2000/svg">
    <rect x="10" y="30" width="180" height="100" rx="10" ry="10" fill="none" stroke="black" stroke-width="5"/>
    <line x1="10" y1="30" x2="100" y2="100" stroke="black" stroke-width="5"/>
    <line x1="190" y1="30" x2="100" y2="100" stroke="black" stroke-width="5"/>
    <line x1="10" y1="130" x2="190" y2="130" stroke="black" stroke-width="5"/>
    <path class="heart" d="M100 90 c-8 -10 -18 -10 -18 0 c0 10 18 30 18 30 s18 -20 18 -30 c0 -10 -10 -10 -18 0z"/>
  </svg>
</div>

<div class="scene" id="scene2">
  <svg viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
    <rect x="0" y="0" width="500" height="500" fill="#fff"/>
    <path d="M110 160 C108 120,108 120,120 110 L380 110 C394 112,394 112,392 150 L392 360 C394 390,388 390,362 392 L132 392 C110 392,110 392,110 360 Z"
          stroke="#000" stroke-width="10" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
    <path d="M110 160 L250 290 L392 160" stroke="#000" stroke-width="10" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
    <path d="M250 300 C235 285,210 285,210 315 C210 340,250 365,250 365 C250 365,290 340,290 315 C290 285,265 285,250 300 Z"
          fill="#ff89b8" stroke="#000" stroke-width="10" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>
</div>

<div class="scene" id="scene3">
  <svg viewBox="0 0 800 800" xmlns="http://www.w3.org/2000/svg">
    <rect x="140" y="90" width="520" height="480" rx="18" fill="#fff" />
    <path d="M90 180 C90 140,110 100,150 95 L650 75 C690 80,710 100,710 150 L710 640 C710 680,690 715,650 725 L150 745 C110 735,90 700,90 660 Z"
          fill="none" stroke="black" stroke-width="16" stroke-linecap="round" stroke-linejoin="round"/>
    <g transform="translate(290,510) scale(1.45)">
      <path class="heart-fill" d="M80 30 C80 -10,20 -10,20 30 C20 60,80 90,80 90 C80 90,140 60,140 30 C140 -10,80 -10,80 30 Z" />
    </g>
    <foreignObject x="170" y="140" width="460" height="380">
      <div xmlns="http://www.w3.org/1999/xhtml" class="note-text">
        don't feel <span class="hl-pink">guilty</span> for not<br>
        being able to handle<br>
        <span class="hl-pink">everything</span>, for needing a<br>
        <span class="underline-blue">break</span>. you need to look<br>
        after yourself. the world<br>
        can wait. 🌍
      </div>
    </foreignObject>
  </svg>
</div>

<div class="scene" id="scene4">
  <svg viewBox="0 0 800 800" xmlns="http://www.w3.org/2000/svg">
    <path d="M150 650 Q120 400 200 300 Q260 240 350 240 Q410 240 450 260 Q480 280 500 320 Q520 360 530 400 Q540 440 540 460 Q540 580 500 640 Q470 680 400 700 Q310 720 200 680 Z"
          fill="none" stroke="#00694e" stroke-width="30" stroke-linecap="round" stroke-linejoin="round" />
    <path d="M210 270 L230 230 L250 270 M260 250 L280 210 L300 250 M310 240 L330 200 L350 240 M360 240 L380 200 L400 240"
          stroke="#00694e" stroke-width="20" stroke-linecap="round" />
    <circle cx="270" cy="320" r="14" fill="#000" />
    <path d="M270 380 Q310 400 360 380" stroke="#00694e" stroke-width="12" fill="none" stroke-linecap="round" />
    <rect x="500" y="350" width="240" height="300" rx="10" ry="10" fill="#fff" stroke="#000" stroke-width="5" transform="rotate(-5 500 350)" />
    <foreignObject x="515" y="360" width="210" height="280" transform="rotate(-5 515 360)">
      <div xmlns="http://www.w3.org/1999/xhtml" class="note-text">
        don't feel <span class="hl-pink">guilty</span> for not<br>
        being able to handle<br>
        <span class="hl-pink">everything</span>, for needing a<br>
        <span class="underline-blue">break</span>. you need to look<br>
        after yourself. the<br>
        world can wait. 🌍
      </div>
    </foreignObject>
  </svg>
</div>

<div class="click-hint">Click anywhere to continue →</div>

<script>
  const scenes = document.querySelectorAll('.scene');
  let current = 0;
  document.body.addEventListener('click', () => {
    scenes[current].classList.remove('active');
    current = (current + 1) % scenes.length;
    scenes[current].classList.add('active');
  });
</script>

</body>
</html>
