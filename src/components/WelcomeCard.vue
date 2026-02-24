<script setup>
</script>

<template>
  <div class="welcome-card">
    <h1>欢迎使用 Vue 3</h1>
    <p>这是一个基于 Vite 的简单 Vue 应用。</p>
  </div>
</template>

<style scoped>
.welcome-card {
  background: linear-gradient(145deg, #2d2d44 0%, #1e1e32 100%);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 16px;
  padding: 2rem;
  text-align: center;
}

.welcome-card h1 {
  font-size: 2rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  background: linear-gradient(90deg, #818cf8, #c084fc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.welcome-card p {
  color: #94a3b8;
  font-size: 1rem;
}
</style>
