<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <!-- 상단 인스타 바 -->
  <header class="topbar">
    <div class="logo">🍽️ food.portfolio</div>
  </header>

  <!-- 스토리 영역 -->
  <div class="stories">
    <div class="story">Poster</div>
    <div class="story">Video</div>
    <div class="story">Goods</div>
  </div>

  <!-- 피드 -->
  <main class="feed">

    <!-- 포스터 -->
    <div class="post">
      <div class="post-header">
        <div class="avatar"></div>
        <span>맛집 포스터</span>
      </div>
      <img src="images/poster.jpg" class="post-img">
      <div class="post-actions">♡ ♥ 💬</div>
      <p class="caption">하늘빛 감성으로 제작한 맛집 포스터 ✨</p>
    </div>

    <!-- 영상 -->
    <div class="post">
      <div class="post-header">
        <div class="avatar"></div>
        <span>홍보 영상</span>
      </div>

      <div class="video-box">
        <video id="video" src="video/promo.mp4"></video>
        <button id="playBtn">▶ Play</button>
      </div>

      <div class="post-actions">♡ ♥ 💬</div>
      <p class="caption">감각적인 맛집 브랜드 필름 🎬</p>
    </div>

    <!-- 굿즈 -->
    <div class="post">
      <div class="post-header">
        <div class="avatar"></div>
        <span>굿즈 디자인</span>
      </div>
      <img src="images/goods.jpg" class="post-img">
      <div class="post-actions">♡ ♥ 💬</div>
      <p class="caption">브랜드 감성을 담은 굿즈 🎁</p>
    </div>

  </main>

</body>
<script src="script.js"></script>
</html>

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI";
  background: #eaf7ff;
}

/* 상단바 */
.topbar {
  position: sticky;
  top: 0;
  background: white;
  padding: 14px;
  text-align: center;
  font-weight: bold;
  border-bottom: 1px solid #ddd;
}

/* 스토리 */
.stories {
  display: flex;
  gap: 10px;
  padding: 12px;
  overflow-x: auto;
  background: white;
}

.story {
  min-width: 60px;
  height: 60px;
  border-radius: 50%;
  background: linear-gradient(135deg, #8fd3ff, #b6e6ff);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  color: white;
}

/* 피드 */
.feed {
  max-width: 420px;
  margin: auto;
}

/* 포스트 카드 */
.post {
  background: white;
  margin: 15px 0;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 20px rgba(0,0,0,0.05);
}

/* 헤더 */
.post-header {
  display: flex;
  align-items: center;
  padding: 12px;
  gap: 10px;
}

.avatar {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background: #8fd3ff;
}

/* 이미지 */
.post-img {
  width: 100%;
}

/* 액션 */
.post-actions {
  padding: 10px;
  font-size: 18px;
}

/* 캡션 */
.caption {
  padding: 0 10px 15px;
  font-size: 14px;
  color: #444;
}

/* 영상 */
.video-box {
  position: relative;
}

video {
  width: 100%;
}

#playBtn {
  position: absolute;
  bottom: 10px;
  left: 10px;
  background: rgba(0,150,255,0.8);
  border: none;
  color: white;
  padding: 8px 14px;
  border-radius: 20px;
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
