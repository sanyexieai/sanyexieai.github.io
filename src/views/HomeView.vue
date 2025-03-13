<script setup lang="ts">
// 定义个人信息数据
const personalInfo = {
  name: '三页写爱',
  title: '全爱开发工程师',
  description: '一页相遇，二页相知，我在第三页等你',
  socialLinks: [
    { name: 'GitHub', url: 'https://github.com/sanyexieai' },
    { name: '小红书', url: 'https://www.xiaohongshu.com/user/profile/5cc8c61800000000160001f2' },
  ]
}

const navItems = [
  { name: '首页', href: '#home' },
  { name: '关于', href: '#about' },
  { name: '作品', href: '#works' },
  { name: '联系', href: '#contact' }
]
</script>

<template>
  <nav class="nav-bar glass-panel">
    <div class="nav-brand">{{ personalInfo.name }}</div>
    <div class="nav-links">
      <a v-for="item in navItems" :key="item.name" :href="item.href" class="nav-link">
        {{ item.name }}
      </a>
    </div>
  </nav>

  <div class="background">
    <div class="film-overlay"></div>
  </div>

  <main class="home">
    <div class="hero glass-panel">
      <h1>{{ personalInfo.name }}</h1>
      <h2>{{ personalInfo.title }}</h2>
      <p class="description">{{ personalInfo.description }}</p>

      <div class="social-links">
        <a v-for="link in personalInfo.socialLinks" :key="link.name" :href="link.url" target="_blank"
          class="social-link glass-button">
          {{ link.name }}
        </a>
      </div>
    </div>
  </main>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@300;400&display=swap');
</style>

<style scoped>
.background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-image: url('@/assets/images/bg.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  z-index: 0;
}

.home {
  min-height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  text-align: left;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  position: relative;
  z-index: 2;
  overflow-x: hidden;
}

.hero {
  max-width: 800px;
  padding: 3rem;
  border-radius: 16px;
  margin-left: 5%;
  position: relative;
  z-index: 2;
}

.glass-panel {
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.2);
  position: relative;
  z-index: 2;
  isolation: isolate;
}

h1 {
  font-family: 'Josefin Sans', sans-serif;
  font-size: 3.5rem;
  color: rgba(229, 231, 235, 0.95);
  margin-bottom: 1rem;
  letter-spacing: 2px;
  font-weight: 300;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
}

h2 {
  font-family: 'Josefin Sans', sans-serif;
  font-size: 1.8rem;
  color: rgba(209, 213, 219, 0.85);
  margin-bottom: 2rem;
  font-weight: 300;
  letter-spacing: 1px;
}

.description {
  font-size: 1.2rem;
  line-height: 1.8;
  color: rgba(209, 213, 219, 0.75);
  margin-bottom: 2.5rem;
  font-weight: 300;
  letter-spacing: 0.5px;
}

.social-links {
  display: flex;
  gap: 1.5rem;
  justify-content: flex-start;
}

.glass-button {
  padding: 0.8rem 2rem;
  color: white;
  text-decoration: none;
  border-radius: 8px;
  transition: all 0.3s ease;
  font-family: 'Josefin Sans', sans-serif;
  letter-spacing: 1px;
  background: rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(5px);
}

.glass-button:hover {
  transform: translateY(-2px);
  background: rgba(0, 0, 0, 0.4);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

@media (max-width: 768px) {
  .hero {
    margin-left: 3%;
    padding: 2rem;
    max-width: 90%;
  }

  h1 {
    font-size: 2.5rem;
  }

  h2 {
    font-size: 1.4rem;
  }

  .description {
    font-size: 1rem;
  }
}

/* 添加导航栏样式 */
.nav-bar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  z-index: 3;
  background: rgba(0, 0, 0, 0.3);
  backdrop-filter: blur(8px);
}

.nav-brand {
  font-family: 'Josefin Sans', sans-serif;
  font-size: 1.5rem;
  color: rgba(229, 231, 235, 0.95);
  letter-spacing: 1px;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: rgba(209, 213, 219, 0.85);
  text-decoration: none;
  font-family: 'Josefin Sans', sans-serif;
  font-size: 1rem;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
  padding: 0.5rem 0;
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: white;
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

@media (max-width: 768px) {
  .nav-bar {
    flex-direction: column;
    padding: 1rem;
  }

  .nav-brand {
    margin-bottom: 1rem;
  }

  .nav-links {
    gap: 1rem;
  }

  .nav-link {
    font-size: 0.9rem;
  }
}

.film-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background:
    repeating-linear-gradient(45deg,
      rgba(255, 255, 255, 0.04) 0px,
      rgba(255, 255, 255, 0.04) 1px,
      transparent 1px,
      transparent 2px),
    repeating-linear-gradient(-45deg,
      rgba(255, 255, 255, 0.04) 0px,
      rgba(255, 255, 255, 0.04) 1px,
      transparent 1px,
      transparent 2px);
  background-size: 2px 2px;
  animation: filmNoise 0.3s steps(2) infinite;
  pointer-events: none;
  backdrop-filter: blur(1.5px);
  background-color: rgba(0, 0, 0, 0.15);
  z-index: 1;
}

@keyframes filmNoise {
  0% {
    background-position: 0 0;
    opacity: 0.8;
  }

  20% {
    background-position: 1px -1px;
    opacity: 0.7;
  }

  40% {
    background-position: -1px 1px;
    opacity: 0.8;
  }

  60% {
    background-position: 1px 1px;
    opacity: 0.7;
  }

  80% {
    background-position: -1px -1px;
    opacity: 0.8;
  }

  100% {
    background-position: 0 0;
    opacity: 0.7;
  }
}

/* 添加全局样式确保页面不会出现滚动条 */
:root {
  overflow-x: hidden;
}

/* 移动端适配 */
@media (max-width: 768px) {
  .film-overlay {
    width: 30%;
  }
}
</style>
