portfolio/
 ├── index.html
 ├── style.css
 ├── script.js
 ├── images/
 │    ├── poster.jpg
 │    ├── goods.jpg
 ├── video/
 │    ├── promo.mp4

 <!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <!-- LOADING -->
  <div class="loader">
    <h1>FOOD PORTFOLIO</h1>
  </div>

  <!-- NAV -->
  <nav>
    <div>🍽 Portfolio</div>
    <div>Poster / Video / Goods</div>
  </nav>

  <!-- SECTION 1 -->
  <section class="section poster">
    <div class="text reveal">
      <h1>Poster Design</h1>
      <p>하늘빛 감성으로 제작된 맛집 포스터</p>
    </div>
    <div class="media reveal">
      <img src="images/poster.jpg">
    </div>
  </section>

  <!-- SECTION 2 -->
  <section class="section video">
    <div class="text reveal">
      <h1>Promo Video</h1>
      <p>브랜드 무드를 담은 영상 콘텐츠</p>
    </div>

    <div class="media reveal">
      <video id="video" src="video/promo.mp4"></video>
      <button id="playBtn">▶ Play</button>
    </div>
  </section>

  <!-- SECTION 3 -->
  <section class="section goods">
    <div class="text reveal">
      <h1>Goods Design</h1>
      <p>브랜드 아이덴티티 굿즈 제작</p>
    </div>
    <div class="media reveal">
      <img src="images/goods.jpg">
    </div>
  </section>

  <script src="script.js"></script>
</body>
</html>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, sans-serif;
}

/* LOADER */
.loader {
  position: fixed;
  width: 100%;
  height: 100vh;
  background: #8fd3ff;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
  animation: fadeOut 1s 1.5s forwards;
}

@keyframes fadeOut {
  to { opacity: 0; visibility: hidden; }
}

/* NAV */
nav {
  position: fixed;
  top: 0;
  width: 100%;
  padding: 15px 40px;
  display: flex;
  justify-content: space-between;
  background: rgba(255,255,255,0.6);
  backdrop-filter: blur(10px);
  z-index: 10;
}

/* SECTION */
.section {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: space-around;
  padding: 60px;
  scroll-snap-align: start;
}

/* 배경 */
.poster {
  background: linear-gradient(120deg, #d9f3ff, #ffffff);
}
.video {
  background: linear-gradient(120deg, #bfe9ff, #eaf7ff);
}
.goods {
  background: linear-gradient(120deg, #a6ddff, #dff5ff);
}

/* TEXT */
.text {
  width: 40%;
}

.text h1 {
  font-size: 50px;
  margin-bottom: 10px;
}

.text p {
  color: #555;
}

/* MEDIA */
.media {
  width: 40%;
}

.media img,
.media video {
  width: 100%;
  border-radius: 20px;
  box-shadow: 0 20px 40px rgba(0,0,0,0.1);
}

/* BUTTON */
#playBtn {
  margin-top: 10px;
  padding: 10px 16px;
  border: none;
  border-radius: 30px;
  background: rgba(0,140,255,0.8);
  color: white;
  cursor: pointer;
}

/* SCROLL ANIMATION */
.reveal {
  opacity: 0;
  transform: translateY(60px);
  transition: all 1s ease;
}

.reveal.active {
  opacity: 1;
  transform: translateY(0);
}

// VIDEO CONTROL
const video = document.getElementById("video");
const btn = document.getElementById("playBtn");

btn.addEventListener("click", () => {
  if (video.paused) {
    video.play();
    btn.textContent = "⏸ Pause";
  } else {
    video.pause();
    btn.textContent = "▶ Play";
  }
});

// SCROLL REVEAL ANIMATION
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add("active");
    }
  });
});

document.querySelectorAll(".reveal").forEach(el => {
  observer.observe(el);
});
