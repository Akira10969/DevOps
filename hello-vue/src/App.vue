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
          <button class="btn btn-secondary" @click="changeTheme">Toggle Theme</button>
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

const showMessage = () => {
  message.value = message.value ? '' : 'Congratulations! Your Vue app is working perfectly!'
}

const changeTheme = () => {
  isDark.value = !isDark.value
  document.documentElement.classList.toggle('dark-theme', isDark.value)
}
</script>

<style scoped>
.app {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 2rem;
  font-family: 'Arial', sans-serif;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.hero {
  text-align: center;
  padding: 4rem 0;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  margin-bottom: 3rem;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}

.title {
  font-size: 3.5rem;
  color: white;
  margin-bottom: 1rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  animation: fadeInUp 1s ease-out;
}

.subtitle {
  font-size: 1.3rem;
  color: rgba(255, 255, 255, 0.9);
  margin-bottom: 2rem;
  animation: fadeInUp 1s ease-out 0.2s both;
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
}

.btn-primary {
  background: linear-gradient(45deg, #42b983, #35495e);
  color: white;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(66, 185, 131, 0.4);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.2);
  color: white;
  border: 2px solid rgba(255, 255, 255, 0.3);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

.message {
  background: rgba(255, 255, 255, 0.2);
  padding: 1rem 2rem;
  border-radius: 10px;
  color: white;
  font-size: 1.1rem;
  margin-top: 1rem;
  animation: slideIn 0.5s ease-out;
}

.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  transition: transform 0.3s ease;
  animation: fadeInUp 1s ease-out 0.6s both;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.feature-card h3 {
  color: white;
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.feature-card p {
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.6;
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
