<template>
  <header class="w-full px-4 sm:px-10 py-4">
    <div class="flex flex-col sm:flex-row items-center justify-between">
      <!-- Mobile menu button (hidden on desktop) -->
      <div class="sm:hidden flex items-center justify-between w-full mb-4">
        <img src="/public/img/header/logo.png" alt="logo" class="w-32" />
        <button @click="toggleMobileMenu" class="text-red-800">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
          </svg>
        </button>
      </div>

      <!-- Navigation (hidden on mobile when menu is closed) -->
     
   <ul
  :class="{ hidden: !mobileMenuOpen, flex: mobileMenuOpen }"
  class="sm:flex flex-col sm:flex-row items-center gap-3 sm:gap-6 uppercase text-sm sm:text-base w-full sm:w-auto text-center"
>
  <li>
    <a 
      href="#about-section" 
      class="hover:text-red-800 transition block py-2 sm:py-0"
      @click.prevent="smoothScroll('about-section')"
    >О компании</a>
  </li>
  <li>
    <a 
      href="#reviews-section" 
      class="hover:text-red-800 transition block py-2 sm:py-0"
      @click.prevent="smoothScroll('reviews-section')"
    >Отзывы</a>
  </li>
  <li>
    <a 
      href="#contacts-section" 
      class="hover:text-red-800 transition block py-2 sm:py-0"
      @click.prevent="smoothScroll('contacts-section')"
    >Контакты</a>
  </li>
  <li>
    <a 
      href="#price-section" 
      class="hover:text-red-800 transition block py-2 sm:py-0"
      @click.prevent="smoothScroll('price-section')"
    >Прайс</a>
  </li>
  <li>
    <a 
      href="#promotions-section" 
      class="hover:text-red-800 transition block py-2 sm:py-0"
      @click.prevent="smoothScroll('promotions-section')"
    >Акции</a>
  </li>
</ul>

      <!-- Logo (hidden on mobile, shown on desktop) -->
      <img
        src="/public/img/header/logo.png"
        alt="logo"
        class="hidden sm:block w-32 lg:w-40 mx-4 lg:mx-10"
      />

      <!-- Contact info and buttons -->
      <div class="hidden sm:flex items-center gap-3 lg:gap-5">
        <h2 class="text-sm lg:text-base font-semibold whitespace-nowrap">+7 (495) 128-46-01</h2>
        <button
          @click="openPopup"
          class="border px-3 py-1 rounded-xl uppercase text-red-800 font-medium text-sm transition duration-200 hover:scale-105 cursor-pointer"
        >
          Обратный звонок
        </button>
        <div class="flex gap-2">
          <img
            src="/public/img/header/Telegram App.svg"
            alt="tg"
            class="w-6 h-6 transition duration-200 hover:scale-105 cursor-pointer"
          />
          <img
            src="/public/img/header/VK com.png"
            alt="vk"
            class="w-6 h-6 transition duration-200 hover:scale-105 cursor-pointer"
          />
        </div>
      </div>

      <!-- Mobile contact button (shown only on mobile) -->
      <div class="sm:hidden w-full mt-4">
        <button
          @click="openPopup"
          class="w-full border px-3 py-2 rounded-xl uppercase text-red-800 font-medium text-sm transition duration-200 hover:scale-105 cursor-pointer"
        >
          Обратный звонок
        </button>
        <div class="flex justify-center gap-4 mt-3">
          <img
            src="/public/img/header/Telegram App.svg"
            alt="tg"
            class="w-6 h-6 transition duration-200 hover:scale-105 cursor-pointer"
          />
          <img
            src="/public/img/header/VK com.png"
            alt="vk"
            class="w-6 h-6 transition duration-200 hover:scale-105 cursor-pointer"
          />
        </div>
      </div>
    </div>
  </header>

  <Popup ref="popupRef">
    <div class="flex flex-col w-full sm:w-96 m-auto mt-5 sm:mt-10 px-4 sm:px-0">
      <p class="text-center text-sm sm:text-base">
        Введите номер телефона; мы свяжемся с Вами в течение 20 минут <br class="hidden sm:block" />
        (рабочее время пн-пт с 9:00 до 18:00) и <br class="hidden sm:block" />
        ответим на все интересующие Вас вопросы.
      </p>
      <input
        type="tel"
        placeholder="+7 (___) ___-__-__"
        class="m-auto mt-4 w-full px-4 py-2 border rounded-lg"
        pattern="\+7\s\(\d{3}\)\s\d{3}-\d{2}-\d{2}"
      />
      <button
        class="m-auto border rounded-3xl w-full sm:w-48 mt-5 py-2 uppercase text-white bg-red-800 transition duration-200 hover:scale-105 cursor-pointer text-sm sm:text-base"
      >
        Отправить
      </button>
    </div>
  </Popup>
</template>

<script setup>
import { ref } from 'vue'
import Popup from './Popup.vue'

const popupRef = ref(null)
const mobileMenuOpen = ref(false)

const openPopup = () => {
  popupRef.value?.open()
}

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}
</script>

<script>
export default {
  methods: {
  smoothScroll(targetId) {
    const targetElement = document.getElementById(targetId);
    if (targetElement) {
      targetElement.scrollIntoView({
        behavior: 'smooth',
        block: 'start'
      });
      
      // Закрываем мобильное меню, если оно открыто
      if (this.mobileMenuOpen) {
        this.mobileMenuOpen = false;
      }
    }
  }
},
  data() {
    return {
      mobileMenuOpen: false
    }
  }
}
</script>

