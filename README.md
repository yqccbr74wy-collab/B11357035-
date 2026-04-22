<!DOCTYPE html>

<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>王耀樟 — 自我介紹</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@300;400;700;900&family=DM+Serif+Display:ital@0;1&display=swap" rel="stylesheet">
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–night: #0d0d1a;
–deep: #12122a;
–mid: #1e1e40;
–glow: #7b6fcf;
–soft: #a89be0;
–moon: #f0e6c8;
–star: #fff8e1;
–mist: rgba(160, 140, 220, 0.12);
}

html, body {
min-height: 100vh;
background: var(–night);
color: var(–moon);
font-family: ‘Noto Serif TC’, serif;
overflow-x: hidden;
}

/* Stars background */
.stars {
position: fixed;
inset: 0;
pointer-events: none;
z-index: 0;
}

.star-dot {
position: absolute;
border-radius: 50%;
background: white;
animation: twinkle var(–dur) ease-in-out infinite;
opacity: 0;
}

@keyframes twinkle {
0%, 100% { opacity: 0; }
50% { opacity: var(–max-op); }
}

/* Floating moon */
.moon {
position: fixed;
top: 6vh;
right: 8vw;
width: 110px;
height: 110px;
border-radius: 50%;
background: radial-gradient(circle at 38% 38%, #fff8e1, #e0c97a 60%, #b89a3a);
box-shadow: 0 0 60px 20px rgba(224, 201, 122, 0.25), 0 0 120px 40px rgba(224, 201, 122, 0.1);
animation: moonFloat 8s ease-in-out infinite;
z-index: 1;
}

@keyframes moonFloat {
0%, 100% { transform: translateY(0); }
50% { transform: translateY(-12px); }
}

/* Clouds / mist */
.cloud {
position: fixed;
border-radius: 100px;
background: linear-gradient(135deg, rgba(123,111,207,0.08), rgba(160,140,220,0.04));
filter: blur(40px);
animation: drift var(–d) ease-in-out infinite alternate;
z-index: 0;
}

@keyframes drift {
from { transform: translateX(0) translateY(0); }
to { transform: translateX(var(–tx)) translateY(var(–ty)); }
}

/* Layout */
.wrapper {
position: relative;
z-index: 2;
min-height: 100vh;
display: flex;
align-items: center;
justify-content: center;
padding: 4rem 1.5rem;
}

.card {
max-width: 680px;
width: 100%;
border: 1px solid rgba(123,111,207,0.25);
background: linear-gradient(160deg, rgba(30,30,64,0.85), rgba(13,13,26,0.95));
backdrop-filter: blur(20px);
padding: 4rem 3.5rem;
position: relative;
animation: fadeUp 1.2s ease both;
}

@keyframes fadeUp {
from { opacity: 0; transform: translateY(30px); }
to { opacity: 1; transform: translateY(0); }
}

.card::before {
content: ‘’;
position: absolute;
top: 0; left: 0; right: 0;
height: 2px;
background: linear-gradient(90deg, transparent, var(–glow), var(–soft), transparent);
}

/* Header */
.eyebrow {
font-size: 0.65rem;
letter-spacing: 0.3em;
text-transform: uppercase;
color: var(–glow);
margin-bottom: 1.2rem;
opacity: 0;
animation: fadeUp 0.8s 0.3s ease both;
}

.name {
font-family: ‘DM Serif Display’, serif;
font-size: clamp(3rem, 8vw, 5rem);
line-height: 1;
letter-spacing: -1px;
color: var(–moon);
margin-bottom: 0.3rem;
opacity: 0;
animation: fadeUp 0.8s 0.5s ease both;
}

.name-en {
font-family: ‘DM Serif Display’, serif;
font-style: italic;
font-size: 1.1rem;
color: var(–soft);
margin-bottom: 2.5rem;
opacity: 0;
animation: fadeUp 0.8s 0.7s ease both;
}

.divider {
width: 48px;
height: 1px;
background: linear-gradient(90deg, var(–glow), transparent);
margin-bottom: 2.5rem;
opacity: 0;
animation: fadeUp 0.8s 0.9s ease both;
}

/* Info pills */
.pills {
display: flex;
flex-wrap: wrap;
gap: 0.6rem;
margin-bottom: 2.5rem;
opacity: 0;
animation: fadeUp 0.8s 1.0s ease both;
}

.pill {
border: 1px solid rgba(123,111,207,0.4);
padding: 0.35rem 0.9rem;
font-size: 0.8rem;
color: var(–soft);
letter-spacing: 0.05em;
border-radius: 100px;
background: rgba(123,111,207,0.06);
}

/* Intro text */
.intro {
font-size: 1.05rem;
line-height: 2.1;
color: rgba(240, 230, 200, 0.85);
opacity: 0;
animation: fadeUp 0.8s 1.1s ease both;
}

.intro p + p {
margin-top: 1.25rem;
}

.highlight {
color: var(–soft);
font-weight: 700;
}

/* ZZZ decoration */
.zzz {
position: absolute;
right: 2.5rem;
bottom: 2.5rem;
display: flex;
gap: 0.3rem;
align-items: flex-end;
opacity: 0.25;
}

.zzz span {
font-family: ‘DM Serif Display’, serif;
color: var(–soft);
animation: zFloat var(–d2) ease-in-out infinite;
line-height: 1;
}

@keyframes zFloat {
0%, 100% { opacity: 0.4; transform: translateY(0); }
50% { opacity: 1; transform: translateY(-6px); }
}

/* Footer */
.footer-line {
margin-top: 3rem;
padding-top: 1.5rem;
border-top: 1px solid rgba(123,111,207,0.15);
display: flex;
justify-content: space-between;
align-items: center;
opacity: 0;
animation: fadeUp 0.8s 1.4s ease both;
}

.school-tag {
font-size: 0.75rem;
color: var(–glow);
letter-spacing: 0.12em;
}

.date-tag {
font-size: 0.7rem;
color: rgba(160,140,220,0.4);
font-style: italic;
}

@media (max-width: 520px) {
.card { padding: 2.5rem 1.75rem; }
.name { font-size: 3rem; }
}
</style>

</head>
<body>

<div class="stars" id="stars"></div>
<div class="moon"></div>

<!-- Clouds -->

<div class="cloud" style="width:500px;height:200px;top:10%;left:-100px;--d:14s;--tx:40px;--ty:20px;"></div>
<div class="cloud" style="width:400px;height:150px;top:60%;right:-80px;--d:18s;--tx:-30px;--ty:-15px;"></div>
<div class="cloud" style="width:300px;height:120px;bottom:5%;left:20%;--d:12s;--tx:20px;--ty:10px;"></div>

<div class="wrapper">
  <div class="card">
    <div class="zzz">
      <span style="font-size:1rem;--d2:2.2s;">z</span>
      <span style="font-size:1.4rem;--d2:2.8s;animation-delay:0.4s;">z</span>
      <span style="font-size:1.9rem;--d2:3.4s;animation-delay:0.8s;">Z</span>
    </div>

```
<div class="eyebrow">✦ 自我介紹 · Self Introduction</div>
<div class="name">王耀樟</div>
<div class="name-en">Wang Yao-Zhang</div>
<div class="divider"></div>

<div class="pills">
  <span class="pill">🏫 屏東科技大學</span>
  <span class="pill">😴 睡覺愛好者</span>
  <span class="pill">🌙 夜貓族</span>
</div>

<div class="intro">
  <p>
    大家好，我叫<span class="highlight">王耀樟</span>，很高興能在這裡認識各位。
    我目前就讀於<span class="highlight">國立屏東科技大學</span>，能來到這個課堂，感到非常期待。
  </p>
  <p>
    說到興趣，我必須誠實——我最愛的事情就是<span class="highlight">睡覺</span>。
    睡覺對我來說不只是休息，更是一門藝術：抓對時機、找到最舒服的姿勢、
    感受意識慢慢飄向夢境的那個瞬間，是一天中最幸福的時刻。
  </p>
  <p>
    雖然我睡眠需求旺盛，但學習起來絕對清醒又認真。
    希望這學期能和大家一起努力，也歡迎跟我聊天——
    當然，如果你也喜歡睡覺，我們肯定有話聊。
    請多指教！
  </p>
</div>

<div class="footer-line">
  <span class="school-tag">國立屏東科技大學 · NPUST</span>
  <span class="date-tag">2026</span>
</div>
```

  </div>
</div>

<script>
// Generate stars
const starsEl = document.getElementById('stars');
for (let i = 0; i < 120; i++) {
  const s = document.createElement('div');
  s.className = 'star-dot';
  const size = Math.random() * 2.5 + 0.5;
  s.style.cssText = `
    width:${size}px; height:${size}px;
    top:${Math.random()*100}%;
    left:${Math.random()*100}%;
    --dur:${(Math.random()*4+2).toFixed(1)}s;
    --max-op:${(Math.random()*0.8+0.2).toFixed(2)};
    animation-delay:${(Math.random()*5).toFixed(1)}s;
  `;
  starsEl.appendChild(s);
}
</script>

</body>
</html>
