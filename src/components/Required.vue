<template>
  <div class="bg-gray-100">
    <h1 class="text-center text-5xl p-15  font-black uppercase">
      Если вам <span class="text-red-800">необходимо</span>:
    </h1>
    <div class="flex gap-30 justify-center">
      <figure class="transition duration-200 hover:scale-105 cursor-pointer">
        <img src="/public/img/main/ico-5.png" alt="" class="m-auto" />
        <figcaption class="w-40 h-25 border-2 border-red-800  text-center pt-3 -mt-3.5 font-medium">
          Увеличить <br />
          узнаваемость <br />
          бренда
        </figcaption>
      </figure>
      <figure class="transition duration-200 hover:scale-105 cursor-pointer">
        <img src="/public/img/main/ico-6.png" alt="" class="m-auto" />
        <figcaption class="w-40 h-25 border-2 border-red-800  text-center pt-3 -mt-3.5 font-medium">
          Прорекламировать новый продукт <br />
          или услугу
        </figcaption>
      </figure>
      <figure class="transition duration-200 hover:scale-105 cursor-pointer">
        <img src="/public/img/main/ico-7.png" alt="" class="m-auto" />
        <figcaption class="w-40 h-25 border-2 border-red-800  text-center pt-3 -mt-3.5 font-medium">
          Привлечь <br />
          новых <br />
          клиентов
        </figcaption>
      </figure>
      <figure class="transition duration-200 hover:scale-105 cursor-pointer">
        <img src="/public/img/main/ico-8.png" alt="" class="m-auto" />
        <figcaption class="w-40 h-25 border-2 border-red-800  text-center pt-3 -mt-3.5 font-medium">
          Сообщить новости: <br />
          изменение адреса, <br />
          открытие офиса
        </figcaption>
      </figure>
    </div>
    <div class="flex gap-20 justify-center mt-5">
      <figure class="transition duration-200 hover:scale-105 cursor-pointer">
        <img src="/public/img/main/ico-9.png" alt="" class="m-auto" />
        <figcaption class="w-65 h-25 border-2 border-red-800  text-center pt-3 -mt-3.5 font-medium">
          Запустить массовую рекламу, <br />
          но нет бюджета <br />
          на медиа
        </figcaption>
      </figure>
      <figure class="transition duration-200 hover:scale-105 cursor-pointer">
        <img src="/public/img/main/ico-10.png" alt="" class="m-auto" />
        <figcaption class="w-65 h-25 border-2 border-red-800  text-center pt-3 -mt-3.5 font-medium">
          Разместить рекламу на чётко <br />
          определённой территории <br />
          (в рамках района или его части)
        </figcaption>
      </figure>
      <figure class="transition duration-200 hover:scale-105 cursor-pointer">
        <img src="/public/img/main/ico-11.png" alt="" class="m-auto" />
        <figcaption class="w-65 h-25 border-2 border-red-800  text-center pt-3 -mt-3.5 font-medium">
          Дополнить полномасштабную <br />
          рекламную кампанию
        </figcaption>
      </figure>
    </div>
    <p class="text-center mt-10">Вам достаточно оставить заявку на нашем сайте, и мы все сделаем за вас!</p>
    <div class="flex w-150 gap-10 m-auto">
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
  </div>
</template>



<script setup>
import { ref } from 'vue'
import Popup from './Popup.vue'

const popupRef = ref(null)

const openPopup = () => {
  popupRef.value?.open()
}
</script>
