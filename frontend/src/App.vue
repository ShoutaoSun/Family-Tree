<template>
  <div class="app">
    <!-- 顶部导航栏 -->
    <header class="site-header">
      <div class="logo">
        <img src="@/assets/logo.svg" alt="Logo" class="logo-img" />
        <span class="logo-text">千枝同根</span>
      </div>
      <nav :class="['nav-links', { show: mobileMenuOpen }]">
        <router-link to="/" class="nav-link">首页</router-link>
        <router-link to="/tree" class="nav-link">家族树</router-link>
        <router-link to="/view" class="nav-link">族谱预览</router-link>
        <router-link to="/image" class="nav-link">影像记忆</router-link>
        <router-link to="/update" class="nav-link">上传信息</router-link>
        <router-link to="/about" class="nav-link">关于我们</router-link>
      </nav>
      <button class="mobile-menu-btn" @click="toggleMenu">☰</button>
    </header>

    <!-- 主体内容 -->
    <main>
      <router-view />
    </main>

    <!-- 页脚 -->
    <footer class="site-footer">
      <div class="footer-content">
        <p>© 2026 | 千枝同根 · 传承家族记忆</p>
      </div>
    </footer>
  </div>

</template>

<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)

const toggleMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}
</script>

<style scoped>
.app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* 头部 */
.site-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background: rgba(255, 255, 245, 0.7);
  backdrop-filter: blur(16px);
  position: sticky;
  top: 0;
  z-index: 100;
  border-bottom: 1px solid rgba(180, 160, 120, 0.2);
  box-shadow: 0 2px 8px rgba(0,0,0,0.02);
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-weight: 600;
  font-size: 1.25rem;
  color: #2c4b2c;
}
.logo-img {
  height: 36px;
  width: auto;
  display: block;
}
.logo-icon {
  font-size: 1.6rem;
}
.logo-text {
  letter-spacing: 1px;
}

.nav-links {
  display: flex;
  gap: 2rem;
}
.nav-link {
  text-decoration: none;
  color: #3a5a40;
  font-weight: 500;
  transition: color 0.2s;
  position: relative;
  padding: 0.25rem 0;
}
.nav-link:hover {
  color: #7c9a6e;
}
.nav-link.router-link-active {
  color: #5b8c5a;
  font-weight: 600;
}
.nav-link.router-link-active::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 2px;
  background: #8ba888;
  border-radius: 2px;
}

.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  font-size: 1.8rem;
  cursor: pointer;
  color: #2c4b2c;
  padding: 0.25rem 0.5rem;
}

/* 页脚 */
.site-footer {
  background: #eef2e6;
  padding: 1.2rem 1rem;
  margin-top: auto;
  border-top: 1px solid #d8e0ce;
}
.footer-content {
  max-width: 1280px;
  margin: 0 auto;
  text-align: center;
  color: #5c6f5c;
  font-size: 0.85rem;
}
.footer-links {
  margin-top: 0.5rem;
}
.footer-links a {
  color: #5c6f5c;
  text-decoration: none;
  margin: 0 0.5rem;
}
.footer-links a:hover {
  color: #2c4b2c;
  text-decoration: underline;
}

/* 响应式 */
@media (max-width: 768px) {
  .site-header {
    padding: 0.8rem 1.2rem;
  }
  .nav-links {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 68px;
    left: 0;
    right: 0;
    background: rgba(255, 255, 245, 0.98);
    backdrop-filter: blur(16px);
    padding: 1.2rem;
    gap: 1rem;
    text-align: center;
    border-bottom: 1px solid #ddd0b0;
    box-shadow: 0 8px 16px rgba(0,0,0,0.05);
  }
  .nav-links.show {
    display: flex;
  }
  .mobile-menu-btn {
    display: block;
  }
  .logo-text {
    font-size: 1rem;
  }
}
</style>
