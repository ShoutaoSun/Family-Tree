<template>
  <div class="home">
    <!-- Hero 主视觉区：左右布局 -->
    <section class="hero">
      <div class="hero-container">
        <!-- 左侧文字区：毛笔风格，左对齐 -->
        <div class="hero-left">
          <h1 class="main-title">千枝同根</h1>
          <div class="decorative-line"></div>
          <p class="subtitle">同根而生，向光而长</p>
          <button class="explore-btn" @click="scrollToFeatures">开始探索家谱</button>
        </div>

        <!-- 右侧图片区 -->
        <div class="hero-right">
          <img src="@/assets/image1.png" class="hero-image" loading="lazy"/>
        </div>
      </div>
    </section>

    <!-- 核心功能卡片区 -->
    <section class="features" ref="featuresSection">
      <div class="container">
        <h1 class="section-title">家族记忆 · 从这里开始</h1>
        <div class="cards-grid">
          <div class="card">
            <div class="card-icon">🌳</div>
            <h3>家族树</h3>
            <p>枝脉分明，一目了然</p>
          </div>
          <div class="card">
            <div class="card-icon">📖</div>
            <h3>族谱预览</h3>
            <p>世系传承，指尖翻阅</p>
          </div>
          <div class="card">
            <div class="card-icon">📸</div>
            <h3>影像记忆</h3>
            <p>岁月留影，家族珍藏</p>
          </div>
          <div class="card">
            <div class="card-icon">📤</div>
            <h3>上传信息</h3>
            <p>共同修谱，续写家史</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const featuresSection = ref(null)

const scrollToFeatures = () => {
  if (featuresSection.value) {
    featuresSection.value.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<style scoped>
/* Hero 区域 */
.hero {
  min-height: 85vh;
  display: flex;
  align-items: center;
  padding: 2rem 2rem;
  background: radial-gradient(circle at 20% 30%, rgba(235, 220, 190, 0.2) 0%, rgba(230, 242, 245, 0.1) 100%),
              linear-gradient(135deg, #fefaf0 0%, #f0f4ea 100%);
}

.hero-container {
  max-width: 1280px;
  margin: 0 auto;
  width: 100%;
  display: flex;
  align-items: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.hero-left {
  flex: 1 1 300px;
  animation: fadeInUp 0.8s ease-out;
  text-align: left; 
}

.hero-right {
  flex: 1 1 300px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-image {
  width: 100%;
  max-width: 680px;
  height: auto;
  aspect-ratio: 4/3;
  object-fit: cover;
  border-radius: 32px;
  box-shadow: 0 24px 40px -16px rgba(40, 60, 30, 0.25),
              0 8px 12px -6px rgba(0,0,0,0.05);
  border: 2px solid rgba(210, 190, 150, 0.25);
  transition: transform 0.4s ease, box-shadow 0.4s;
  background: #e2e6dd;
}

.hero-image:hover {
  transform: scale(1.01);
  box-shadow: 0 30px 50px -18px #3a5e3a40;
  border-color: #cbbd96;
}

/* ===== 动画 ===== */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.main-title {
  font-size: clamp(3rem, 12vw, 5.5rem);
  font-weight: 200;
  font-family: "XuanZongFont";
  background: linear-gradient(135deg, #2c5e2d, #6b8c5c, #c2a575);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  letter-spacing: -0.02em;
  margin-bottom: 0.5rem;
}

.subtitle {
  font-family: "DingLieFont";
  font-size: clamp(1rem, 4vw, 1.8rem);
  font-weight: 400;
  color: #5b6e5a;
  letter-spacing: 0.4em;
  margin-bottom: 2rem;
}

.decorative-line {
  width: 400px;
  height: 2.2px;
  background: linear-gradient(90deg, #b5c9a2, #8ba888, #b5c9a2);
  margin: 1.2rem 0;
  border-radius: 2px;
}

.hero-description {
  font-size: 1.1rem;
  color: #3e5a47;
  line-height: 1.6;
  margin-bottom: 2rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.explore-btn {
  background: rgba(255, 248, 235, 0.8);
  backdrop-filter: blur(8px);
  border: 1px solid rgba(110, 130, 90, 0.4);
  padding: 0.8rem 2rem;
  font-size: 1rem;
  font-weight: 500;
  color: #2c4b2c;
  border-radius: 40px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
}

.explore-btn:hover {
  background: linear-gradient(135deg, #faf3e0, #dce8d5, #bdd0b2);
  color: #2c5e2d;
  transform: translateY(-4px);
  box-shadow: 0 16px 28px rgba(80, 110, 70, 0.12);
  border-color: #bdd0b2;
}

.explore-btn:active {
  background: linear-gradient(135deg, #f7f0dd, #d9e5ce, #b8ceac);
  color: #2c5e2d;
  border-color: #9fb898;
  transform: translateY(-1px);
  box-shadow: 0 6px 12px rgba(80, 110, 70, 0.12);
  transition: all 0.1s ease;
}

/* 特性卡片区 */
.features {
  padding: 4rem 0;
  background: #ffffffcc;
  backdrop-filter: blur(2px);
}

.section-title {
  text-align: center;
  font-size: clamp(1.8rem, 5vw, 2.5rem);
  font-weight: 600;
  color: #2c4b2c;
  margin-bottom: 3rem;
  letter-spacing: -0.01em;
}

.cards-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  padding: 0 1rem;
}

@media (min-width: 640px) {
  .cards-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .cards-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.card {
  background: rgba(255, 255, 245, 0.8);
  backdrop-filter: blur(8px);
  border-radius: 28px;
  padding: 2rem 1.5rem;
  text-align: center;
  transition: all 0.3s;
  border: 1px solid rgba(200, 180, 130, 0.3);
  box-shadow: 0 8px 20px rgba(0,0,0,0.03);
}

.card:hover {
  transform: translateY(-6px);
  background: rgba(255, 255, 245, 0.95);
  border-color: #cbbd96;
  box-shadow: 0 20px 30px -12px rgba(0,0,0,0.12);
}

.card-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.card h3 {
  font-size: 1.4rem;
  margin-bottom: 0.75rem;
  color: #2c4b2c;
}

.card p {
  color: #5c6f5c;
  line-height: 1.4;
  font-size: 0.95rem;
}

/* 引言区 */
.quote {
  padding: 3rem 1rem;
  background: #eef3e8;
  text-align: center;
}

.quote-box {
  max-width: 800px;
  margin: 0 auto;
}

.quote-text {
  font-size: clamp(1.2rem, 4vw, 1.8rem);
  font-style: italic;
  color: #3a5a40;
  line-height: 1.4;
  margin-bottom: 1rem;
  font-weight: 400;
}

.quote-author {
  color: #7c8f7c;
  font-size: 0.9rem;
  letter-spacing: 1px;
}

/* 动画 */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 响应式微调 */
@media (max-width: 768px) {
  .hero {
    min-height: 70vh;
    padding: 1.5rem;
  }
  .hero-description {
    font-size: 0.95rem;
    padding: 0 0.5rem;
  }
  .features {
    padding: 2rem 0;
  }
  .card {
    padding: 1.5rem 1rem;
  }
}
</style>