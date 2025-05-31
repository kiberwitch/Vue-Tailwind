<template>
  <main>
    <section>
      <div class="relative">
        <!-- Основное изображение -->
        <img src="/public/img/main/1.jpg" alt="" class="w-full" />

        <!-- Контент поверх изображения -->
        <div class="absolute inset-0 flex flex-col items-start p-4 md:pl-20 md:pt-10">
          <!-- Верхний текст -->
          <p class="text-sm md:text-base font-medium mb-2 md:mb-4">
            Ваша компания предлагает товары и услуги населению?
          </p>

          <!-- Заголовок -->
          <h1 class="text-2xl md:text-5xl uppercase text-red-800 font-medium mb-4 md:mb-8">
            Разместим вашу рекламу на <br class="hidden md:block" />
            стендах в подъездах жилых <br class="hidden md:block" />
            домов Москвы!
          </h1>

          <!-- Цена и кнопка -->
          <div class="flex flex-col md:flex-row items-start md:items-center gap-4 mb-4 md:mb-8">
            <h3 class="text-lg md:text-xl italic text-red-800">От 7.2 руб. в сутки за 1 стенд</h3>
            <button
              class="border px-4 py-2 rounded-3xl uppercase text-white bg-red-800 text-xs transition duration-200 hover:scale-105 cursor-pointer"
            >
              ПРАЙС-ЛИСТ
            </button>
          </div>

          <!-- Описание -->
          <p class="text-sm md:text-lg font-medium mb-4 md:mb-8">
            Вам больше не нужно разыскивать потенциальных клиентов.
            <br class="hidden md:block" />
            Мы сами придём к ним в гости и расскажем о вас. <br class="hidden md:block" />
            В каждый дом.
          </p>

          <!-- Иконки -->
          <div class="hidden md:flex flex-wrap gap-4 mb-4 md:mb-0">
            <img
              src="/public/img/main/ico-1.png"
              alt=""
              class="transition duration-200 hover:scale-105 cursor-pointer"
            />
            <img
              src="/public/img/main/ico-2.png"
              alt=""
              class="transition duration-200 hover:scale-105 cursor-pointer"
            />
            <img
              src="/public/img/main/ico-3.png"
              alt=""
              class="transition duration-200 hover:scale-105 cursor-pointer"
            />
            <img
              src="/public/img/main/ico-4.png"
              alt=""
              class="transition duration-200 hover:scale-105 cursor-pointer"
            />
          </div>
        </div>

        <!-- Баннер (только на десктопе) -->
        <div class="hidden md:block absolute right-0 top-0 w-60 mr-25">
          <img src="/public/img/main/banner.jpg" alt="" class="w-full transition duration-200 hover:scale-105 cursor-pointer" />

          <!-- Форма -->
          <div class="flex flex-col text-center w-70 py-5 px-5 border bg-white mt-4">
            <p class="text-sm">
              Оформите заявку прямо сейчас
              <br />
              и получите
              <span class="text-red-400"
                >гарантированную скидку <br />
                5% </span
              >на первое размещение <br />
              вашей рекламы!
            </p>

            <input
              type="tel"
              placeholder="+7 (___) ___-__-__"
              class="w-4/5 m-auto mt-2 p-2 border rounded"
              pattern="\+7\s\(\d{3}\)\s\d{3}-\d{2}-\d{2}"
            />

            <button
              @click="openPopup"
              class="m-auto border rounded-3xl w-4/5 mt-2 py-2 uppercase text-white bg-red-800 transition duration-200 hover:scale-105 cursor-pointer text-sm"
            >
              Оформить заявку
            </button>
          </div>
        </div>

        <!-- Форма для мобильных (под основным контентом) -->
        <div class="md:hidden w-full p-4 mt-4 border bg-white">
          <div class="flex flex-col text-center">
            <p class="text-sm">
              Оформите заявку прямо сейчас
              <br />
              и получите
              <span class="text-red-400"
                >гарантированную скидку <br />
                5% </span
              >на первое размещение <br />
              вашей рекламы!
            </p>

            <input
              type="tel"
              placeholder="+7 (___) ___-__-__"
              class="w-full m-auto mt-2 p-2 border rounded"
              pattern="\+7\s\(\d{3}\)\s\d{3}-\d{2}-\d{2}"
            />

            <button
              @click="openPopup"
              class="m-auto border rounded-3xl w-full mt-2 py-2 uppercase text-white bg-red-800 transition duration-200 hover:scale-105 cursor-pointer text-sm"
            >
              Оформить заявку
            </button>
          </div>
        </div>

        <Popup ref="popupRef">
          <div class="flex flex-col w-full sm:w-96 m-auto mt-5 sm:mt-10 px-4 sm:px-0">
            <p class="text-center text-sm sm:text-base">
              Введите номер телефона; мы свяжемся с Вами в течение 20 минут
              <br class="hidden sm:block" />
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
      </div>
    </section>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import Popup from './Popup.vue'

const popupRef = ref(null)

const openPopup = () => {
  popupRef.value?.open()
}
</script>

<style scoped>
/* Дополнительные стили при необходимости */
@media (max-width: 768px) {
  .absolute {
    position: relative;
    inset: auto;
  }
}
</style>
