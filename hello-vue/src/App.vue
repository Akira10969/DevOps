<template>
  <div class="app">
    <div class="container">
      <div class="hero">
        <h1 class="title">
          Hello World from Vue!
        </h1>
        <p class="subtitle">
          Welcome to your awesome Vue.js application
        </p>
        <p class="custom-text">
          Okay - This is a custom message added for demonstration purposes. You can edit or remove this text as you like!
        </p>
        <div class="buttons">
          <button class="btn btn-primary" @click="showMessage">Get Started</button>
          <button class="btn btn-secondary" @click="changeTheme">
            Toggle Theme
            <span v-if="isDark" class="theme-indicator">🌙</span>
            <span v-else class="theme-indicator">☀️</span>
          </button>
        </div>
        <div class="counter-section">
          <button class="btn btn-primary" @click="count++">Click Me!</button>
          <span class="counter-label">You clicked {{ count }} times.</span>
        </div>
        <div v-if="message" class="message">
          {{ message }}
        </div>
      </div>
      <div class="features">
        <div class="feature-card">
          <div class="icon">F</div>
          <h3>Fast</h3>
          <p>Lightning fast development with Vite</p>
        </div>
        <div class="feature-card">
          <div class="icon">B</div>
          <h3>Beautiful</h3>
          <p>Modern and responsive design</p>
        </div>
        <div class="feature-card">
          <div class="icon">F</div>
          <h3>Flexible</h3>
          <p>Easy to customize and extend</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const message = ref('')
const isDark = ref(false)
const count = ref(0)

const showMessage = () => {
  message.value = message.value ? '' : 'Congratulations! Your Vue app is working perfectly!'
}

const changeTheme = () => {
  isDark.value = !isDark.value
  document.documentElement.classList.toggle('dark-theme', isDark.value)
}
</script>

<style scoped>
/* Minimalist Black & White Theme with Dark Mode */
.app {
  min-height: 100vh;
  background: #fff;
  color: #111;
  padding: 2rem;
  font-family: 'Arial', sans-serif;
  transition: background 0.3s, color 0.3s;
}
.dark-theme .app {
  background: #111;
  color: #fff;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.hero {
  text-align: center;
  padding: 4rem 0;
  background: #f7f7f7;
  border-radius: 20px;
  margin-bottom: 3rem;
  box-shadow: 0 4px 16px rgba(0,0,0,0.04);
  transition: background 0.3s;
}
.dark-theme .hero {
  background: #181818;
  box-shadow: 0 4px 16px rgba(255,255,255,0.04);
}

.title {
  font-size: 3.5rem;
  color: inherit;
  margin-bottom: 1rem;
  font-weight: bold;
  animation: fadeInUp 1s ease-out;
}

.subtitle {
  font-size: 1.3rem;
  color: #888;
  margin-bottom: 2rem;
  animation: fadeInUp 1s ease-out 0.2s both;
}
.dark-theme .subtitle {
  color: #bbb;
}

.buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin-bottom: 2rem;
  animation: fadeInUp 1s ease-out 0.4s both;
}

.btn {
  padding: 12px 24px;
  border: none;
  border-radius: 50px;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 600;
  background: #111;
  color: #fff;
}
.btn:hover {
  background: #fff;
  color: #111;
  border: 1px solid #111;
}
.dark-theme .btn {
  background: #fff;
  color: #111;
}
.dark-theme .btn:hover {
  background: #111;
  color: #fff;
  border: 1px solid #fff;
}

.counter-section {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 2rem;
}
.counter-label {
  color: inherit;
  font-size: 1.2rem;
  font-weight: 500;
}
.theme-indicator {
  margin-left: 0.5rem;
  font-size: 1.2rem;
}

.message {
  background: #eee;
  padding: 1rem 2rem;
  border-radius: 10px;
  color: #111;
  font-size: 1.1rem;
  margin-top: 1rem;
  animation: slideIn 0.5s ease-out;
}
.dark-theme .message {
  background: #222;
  color: #fff;
}

.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}
.feature-card {
  background: #fff;
  border: 1px solid #eee;
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease, background 0.3s;
  animation: fadeInUp 1s ease-out 0.6s both;
  cursor: pointer;
}
.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 32px rgba(0,0,0,0.08);
  background: #f7f7f7;
}
.dark-theme .feature-card {
  background: #181818;
  border: 1px solid #333;
}
.dark-theme .feature-card:hover {
  background: #222;
  box-shadow: 0 8px 32px rgba(255,255,255,0.08);
}
.icon {
  font-size: 3rem;
  margin-bottom: 1rem;
  color: #111;
}
.dark-theme .icon {
  color: #fff;
}
.feature-card h3 {
  color: inherit;
  font-size: 1.5rem;
  margin-bottom: 1rem;
}
.feature-card p {
  color: #888;
  line-height: 1.6;
}
.dark-theme .feature-card p {
  color: #bbb;
}

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
@keyframes slideIn {
  from {
    opacity: 0;
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
@media (max-width: 768px) {
  .title {
    font-size: 2.5rem;
  }
  .buttons {
    flex-direction: column;
    align-items: center;
  }
  .features {
    grid-template-columns: 1fr;
  }
}
</style>
