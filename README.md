<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <!-- SECTION 1: POSTER -->
  <section class="section poster">
    <div class="left">
      <h1>01<br>Poster Design</h1>
      <p>하늘빛 무드로 제작한 맛집 포스터</p>
    </div>

    <div class="right">
      <img src="images/poster.jpg" alt="poster">
    </div>
  </section>

  <!-- SECTION 2: VIDEO -->
  <section class="section video">
    <div class="left">
      <h1>02<br>Promo Video</h1>
      <p>브랜드 감성을 담은 영상 콘텐츠</p>
    </div>

    <div class="right">
      <div class="video-box">
        <video id="video" src="video/promo.mp4"></video>
        <button id="playBtn">Play</button>
      </div>
    </div>
  </section>

  <!-- SECTION 3: GOODS -->
  <section class="section goods">
    <div class="left">
      <h1>03<br>Goods Design</h1>
      <p>브랜드 아이덴티티를 담은 굿즈</p>
    </div>

    <div class="right">
      <img src="images/goods.jpg" alt="goods">
    </div>
  </section>

  <script src="script.js"></script>
</body>
</html>

/* 전체 스크롤 스냅 */
body {
  margin: 0;
  font-family: Arial, sans-serif;
  scroll-snap-type: y mandatory;
  overflow-y: scroll;
  background: #eaf7ff;
}

/* 섹션 = 한 화면 */
.section {
  height: 100vh;
  display: flex;
  scroll-snap-align: start;
}

/* 좌측 텍스트 */
.left {
  width: 40%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 60px;
}

.left h1 {
  font-size: 48px;
  margin: 0;
  line-height: 1.2;
}

.left p {
  margin-top: 20px;
  color: #555;
}

/* 우측 비주얼 */
.right {
  width: 60%;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* 이미지 */
.right img {
  width: 80%;
  border-radius: 20px;
  box-shadow: 0 20px 40px rgba(0,0,0,0.1);
}

/* 비디오 */
.video-box {
  position: relative;
  width: 80%;
}

video {
  width: 100%;
  border-radius: 20px;
}

#playBtn {
  position: absolute;
  bottom: 15px;
  left: 15px;
  padding: 10px 16px;
  border: none;
  border-radius: 30px;
  background: rgba(0,140,255,0.8);
  color: white;
  cursor: pointer;
}

/* 섹션별 하늘색 톤 변화 */
.poster {
  background: linear-gradient(120deg, #d9f3ff, #ffffff);
}

.video {
  background: linear-gradient(120deg, #bfe9ff, #eaf7ff);
}

.goods {
  background: linear-gradient(120deg, #a6ddff, #dff5ff);
}

const video = document.getElementById("video");
const btn = document.getElementById("playBtn");

btn.addEventListener("click", () => {
  if (video.paused) {
    video.play();
    btn.textContent = "Pause";
  } else {
    video.pause();
    btn.textContent = "Play";
  }
});
