<template>
  <div class="home">
    <!-- Hero 主视觉区 -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="main-title">千枝同根</h1>
        <p class="subtitle">同根而生，向光而长</p>
        <div class="decorative-line"></div>
        <p class="hero-description">
          追溯血脉之源，铭记家族故事。<br />
          在这里，每一支都来自同一片沃土。
        </p>
        <button class="explore-btn" @click="scrollToFeatures">探索家谱</button>
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
            <div class="card-icon">🖼️</div>
            <h3>影像记忆</h3>
            <p>岁月留影，家族珍藏</p>
          </div>
          <div class="card">
            <div class="card-icon">🤝</div>
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
  justify-content: center;
  text-align: center;
  background: radial-gradient(circle at 20% 30%, rgba(235, 220, 190, 0.2) 0%, rgba(230, 242, 245, 0.1) 100%),
              linear-gradient(135deg, #fefaf0 0%, #f0f4ea 100%);
  padding: 2rem;
}

.hero-content {
  max-width: 900px;
  animation: fadeInUp 0.8s ease-out;
}

.main-title {
  font-size: clamp(3rem, 12vw, 5.5rem);
  font-weight: 800;
  background: linear-gradient(135deg, #2c5e2d, #6b8c5c, #c2a575);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  letter-spacing: -0.02em;
  margin-bottom: 0.5rem;
}

.subtitle {
  font-size: clamp(1rem, 4vw, 1.8rem);
  font-weight: 400;
  color: #5b6e5a;
  letter-spacing: 0.15em;
  margin-bottom: 1rem;
}

.decorative-line {
  width: 70px;
  height: 2px;
  background: linear-gradient(90deg, #b5c9a2, #8ba888, #b5c9a2);
  margin: 1.2rem auto;
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
  background: #fff7e8;
  transform: translateY(-3px);
  box-shadow: 0 12px 24px rgba(0,0,0,0.1);
  border-color: #8ba888;
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