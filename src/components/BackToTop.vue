<template>
    <button
      v-show="isVisible"
      @click="scrollToTop"
      class="fixed bottom-8 right-8 bg-red-800 text-white p-3 rounded-full shadow-lg hover:bg-red-700 transition-all duration-300 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-opacity-50"
      aria-label="Наверх"
    >
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
      </svg>
    </button>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isVisible: false,
        scrollThreshold: 300 // Кнопка появляется после прокрутки на 300px
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll)
    },
    beforeDestroy() {
      window.removeEventListener('scroll', this.handleScroll)
    },
    methods: {
      handleScroll() {
        this.isVisible = window.pageYOffset > this.scrollThreshold
      },
      scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        })
        
        // Альтернатива с кастомной анимацией (если нужно больше контроля)
        // this.customScrollToTop()
      },
      customScrollToTop() {
        const startPosition = window.pageYOffset
        const duration = 500 // Длительность анимации в ms
        const startTime = performance.now()
  
        const animateScroll = (currentTime) => {
          const elapsedTime = currentTime - startTime
          const progress = Math.min(elapsedTime / duration, 1)
          const ease = this.easeOutCubic(progress)
          
          window.scrollTo(0, startPosition * (1 - ease))
          
          if (progress < 1) {
            requestAnimationFrame(animateScroll)
          }
        }
  
        requestAnimationFrame(animateScroll)
      },
      easeOutCubic(t) {
        return (--t) * t * t + 1
      }
    }
  }
  </script>