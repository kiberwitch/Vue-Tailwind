<template>
  <transition name="popup">
    <div v-if="isOpen" class="popup-container">
      <!-- Затемненный фон -->
      <div class="popup-backdrop" @click="close"></div>

      <!-- Сам попап (появляется сверху) -->
      <div class="popup-content">
        <slot></slot>
        <button @click="close" class="popup-close-button" aria-label="Закрыть">&times;</button>
      </div>
    </div>
  </transition>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isOpen = ref(false)

const open = () => {
  isOpen.value = true
  document.body.style.overflow = 'hidden'
}

const close = () => {
  isOpen.value = false
  document.body.style.overflow = ''
}

// Закрытие по ESC
const handleKeydown = (e) => {
  if (e.key === 'Escape') close()
}

onMounted(() => {
  window.addEventListener('keydown', handleKeydown)
})

onUnmounted(() => {
  window.removeEventListener('keydown', handleKeydown)
})

defineExpose({ open, close })
</script>

<style scoped>
.popup-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1000;
  display: flex;
  justify-content: center;
}

.popup-backdrop {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 300%;
  background-color: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(2px);
}

.popup-content {
  position: relative;
  background: white;
  width: 30%;
  height: 30%;
  max-width: 800px;
  max-height: 80vh;
  margin-top: 20px;
  border-radius: 0 0 12px 12px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
  overflow-y: auto;
  z-index: 1001;
  animation: slideDown 0.3s ease-out;
}

.popup-close-button {
  position: absolute;
  top: 12px;
  right: 12px;
  font-size: 24px;
  background: none;
  border: none;
  cursor: pointer;
  color: #666;
  transition: color 0.2s;
}

.popup-close-button:hover {
  color: #333;
}

/* Анимации */
.popup-enter-active .popup-content,
.popup-leave-active .popup-content {
  transition:
    transform 0.3s ease,
    opacity 0.3s ease;
}

.popup-enter-from .popup-content,
.popup-leave-to .popup-content {
  transform: translateY(-100%);
  opacity: 0;
}

.popup-enter-active .popup-backdrop,
.popup-leave-active .popup-backdrop {
  transition: opacity 0.3s ease;
}

.popup-enter-from .popup-backdrop,
.popup-leave-to .popup-backdrop {
  opacity: 0;
}

@keyframes slideDown {
  from {
    transform: translateY(-100%);
  }
  to {
    transform: translateY(0);
  }
}
</style>
