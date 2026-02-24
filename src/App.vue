<script setup>
import { ref } from 'vue'
import WelcomeCard from './components/WelcomeCard.vue'

const count = ref(0)
</script>

<template>
  <div class="app">
    <WelcomeCard />
    <div class="counter-card">
      <h2>计数器示例</h2>
      <p>点击按钮增加计数：{{ count }}</p>
      <button @click="count++">+1</button>
    </div>
  </div>
</template>

<style scoped>
.app {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.counter-card {
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  padding: 1.5rem;
}

.counter-card h2 {
  font-size: 1.25rem;
  margin-bottom: 0.75rem;
  color: #a5b4fc;
}

.counter-card p {
  margin-bottom: 1rem;
  color: #c4b5fd;
}

.counter-card button {
  padding: 0.5rem 1.25rem;
  font-size: 1rem;
  background: #6366f1;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.2s;
}

.counter-card button:hover {
  background: #4f46e5;
}
</style>
