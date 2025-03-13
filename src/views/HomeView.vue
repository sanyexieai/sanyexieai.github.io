<script setup lang="ts">
// 定义个人信息数据
const personalInfo = {
  name: '您的名字',
  title: '职业头衔',
  description: '个人简介：热爱技术、热爱生活...',
  socialLinks: [
    { name: 'GitHub', url: 'https://github.com/yourusername' },
    { name: '微博', url: 'https://weibo.com/yourusername' },
  ]
}
</script>

<template>
  <main class="home">
    <div class="hero">
      <h1>{{ personalInfo.name }}</h1>
      <h2>{{ personalInfo.title }}</h2>
      <p class="description">{{ personalInfo.description }}</p>

      <div class="social-links">
        <a v-for="link in personalInfo.socialLinks" :key="link.name" :href="link.url" target="_blank"
          class="social-link">
          {{ link.name }}
        </a>
      </div>
    </div>
  </main>
</template>

<style scoped>
.home {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 2rem;
}

.hero {
  max-width: 800px;
}

h1 {
  font-size: 3rem;
  color: #2c3e50;
  margin-bottom: 1rem;
}

h2 {
  font-size: 1.5rem;
  color: #42b883;
  margin-bottom: 2rem;
}

.description {
  font-size: 1.2rem;
  line-height: 1.6;
  color: #666;
  margin-bottom: 2rem;
}

.social-links {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.social-link {
  padding: 0.5rem 1rem;
  background-color: #42b883;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  transition: background-color 0.3s;
}

.social-link:hover {
  background-color: #3aa876;
}
</style>
