<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <!-- 첫 화면: 포스터 -->
  <section class="page poster">
    <div class="content">
      <h1>📌 Poster Design</h1>
      <img src="images/poster.jpg" alt="poster">
      <p>하늘빛 감성으로 제작한 맛집 포스터</p>
    </div>
  </section>

  <!-- 두 번째: 영상 -->
  <section class="page video">
    <div class="content">
      <h1>🎬 Promo Video</h1>

      <div class="video-box">
        <video id="video" src="video/promo.mp4"></video>
        <button id="playBtn">▶ Play</button>
      </div>

      <p>브랜드 무드를 담은 홍보 영상</p>
    </div>
  </section>

  <!-- 세 번째: 굿즈 -->
  <section class="page goods">
    <div class="content">
      <h1>🎁 Goods Design</h1>
      <img src="images/goods.jpg" alt="goods">
      <p>브랜드 아이덴티티를 담은 굿즈</p>
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
}

/* 각 페이지 */
.page {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  scroll-snap-align: start;
  text-align: center;
  padding: 40px;
}

/* 하늘색 계열 배경 */
.poster {
  background: linear-gradient(180deg, #d9f3ff, #ffffff);
}

.video {
  background: linear-gradient(180deg, #bfe9ff, #eaf7ff);
}

.goods {
  background: linear-gradient(180deg, #a6ddff, #dff5ff);
}

/* 콘텐츠 박스 */
.content {
  max-width: 700px;
}

/* 이미지 */
img {
  width: 100%;
  border-radius: 20px;
  margin-top: 20px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

/* 영상 */
.video-box {
  position: relative;
  margin-top: 20px;
}

video {
  width: 100%;
  border-radius: 20px;
}

/* 버튼 */
#playBtn {
  position: absolute;
  bottom: 20px;
  left: 20px;
  padding: 10px 16px;
  border: none;
  border-radius: 30px;
  background: rgba(0,140,255,0.8);
  color: white;
  cursor: pointer;
}

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
