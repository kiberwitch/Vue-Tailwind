<template>
  <div class="carousel-container">
    <div class="carousel-track" :style="{ transform: `translateX(-${offset}px)` }">
      <img 
        v-for="(image, index) in extendedImages" 
        :key="index" 
        :src="image" 
        :alt="'Slide ' + (index % images.length + 1)"
        class="carousel-image"
      />
    </div>
  </div>

</template>

<script>
export default {
  name: 'SeamlessCarousel',
  data() {
    return {
      offset: 0,
      animationFrameId: null,
      images: [
        '/public/img/main/slider/1.png',
        '/public/img/main/slider/2.png',
        '/public/img/main/slider/3.png',
        '/public/img/main/slider/4.png',
        '/public/img/main/slider/5.png',
        '/public/img/main/slider/6.png',
        '/public/img/main/slider/7.png',
        '/public/img/main/slider/8.png',
        '/public/img/main/slider/9.png',
        '/public/img/main/slider/10.png',
        '/public/img/main/slider/11.png',
        '/public/img/main/slider/12.png',
        '/public/img/main/slider/13.png',
      ],
      speed: 2, // Скорость прокрутки (пикселей за кадр)
      imageWidth: 100// Ширина одного изображения (нужно задать явно)
    }
  },
  computed: {
    extendedImages() {
      // Дублируем массив изображений для бесшовного перехода
      return [...this.images, ...this.images];
    }
  },
  mounted() {
    this.startAnimation();
    window.addEventListener('resize', this.handleResize);
  },
  beforeUnmount() {
    this.stopAnimation();
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    startAnimation() {
      const animate = () => {
        this.offset += this.speed;
        
        // Когда дошли до конца дублированного набора - переключаемся на начало
        if (this.offset >= this.imageWidth * this.images.length) {
          this.offset = 0;
        }
        
        this.animationFrameId = requestAnimationFrame(animate);
      };
      animate();
    },
    stopAnimation() {
      if (this.animationFrameId) {
        cancelAnimationFrame(this.animationFrameId);
      }
    },
    handleResize() {
      // Можно добавить логику для адаптации под разные размеры экрана
    }
  }
}
</script>

<style scoped>
.carousel-container {
  display: flex;
  align-items: center;
  width: 100%;
  overflow: hidden;
  position: relative;
}

.carousel-track {
  display: flex;
  will-change: transform;
  gap: 40px; /* Добавляем отступ между элементами */
  padding-left: 20px; /* Небольшой отступ слева для первого изображения */
  
}

.carousel-image {
  width: 100px; /* Должно соответствовать значению imageWidth в data */
  height: 100%;
  flex-shrink: 0;
  transition: all 0.2s ease;
  
}

.carousel-image:hover {
  transform: scale(1.05);
}
</style>