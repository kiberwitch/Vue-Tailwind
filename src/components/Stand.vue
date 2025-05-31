<template>
  <main>
    <section>
      <div class="w-full">
        <div class="flex flex-col justify-center w-max m-auto">
            <h1 class="font-black uppercase text-5xl my-5">Какой он − <span class="text-red-800">стенд?</span></h1>
        <p class="text-gray-400 text-lg text-center my-5">
          Рекламные стенды установлены снаружи (около входной двери) <br />
          и/или внутри подъезда (рядом с лифтом или почтовыми ящиками)
        </p>
        </div>
        
        <div class="flex mx-5">
          <div class="flex flex-1">
            <img src="/public/img/main/9.png" alt="" />
          </div>
          <div class="flex flex-col gap-10 flex-1 w-max h-max my-auto ">
            <div class="flex gap-3 relative transition duration-200 hover:scale-105 cursor-pointer">
              <img src="/public/img/main/ico-12.svg" alt="" class="absolute -left-18 -bottom-4" />
              <p>Емкость стенда 9 форматов А4 (210мм*297мм)</p>
            </div>
            <div class="flex gap-3 relative transition duration-200 hover:scale-105 cursor-pointer">
              <img src="/public/img/main/ico-12.svg" alt="" class="absolute -left-18 bottom-3" />
              <p>
                Возможно размещение рекламных форматов А2, А3, А4, а <br />
                также эксклюзивного формата типа «полоса» 3*А4 размером <br />
                630мм*297мм
              </p>
            </div>
            <div class="flex gap-3 relative transition duration-200 hover:scale-105 cursor-pointer">
              <img src="/public/img/main/ico-12.svg" alt="" class="absolute -left-18 -bottom-1" />
              <p>
                Все информационные конструкции имеют единое <br />
                узнаваемое оформление
              </p>
            </div>
            <div class="flex gap-3 relative transition duration-200 hover:scale-105 cursor-pointer">
              <img src="/public/img/main/ico-12.svg" alt="" class="absolute -left-18 -bottom-1" />
              <p>
                Каждая конструкция имеет уникальный ID и оснащена <br />
                индивидуальным QR−кодом
              </p>
            </div>
            <div class="flex gap-3 relative transition duration-200 hover:scale-105 cursor-pointer">
              <img src="/public/img/main/ico-12.svg" alt="" class="absolute -left-18 -bottom-1" />
              <p>
                Информация размещается под стеклом и защищена <br />
                запорным устройством
              </p>
            </div>
            <div class="flex gap-3 relative transition duration-200 hover:scale-105 cursor-pointer">
              <img src="/public/img/main/ico-12.svg" alt="" class="absolute -left-18 bottom-5" />
              <p>
                Наши стенды устанавливаются в каждом подъезде города, <br />
                включая новую Москву. Более 100 000 стендов, но вы <br />
                можете выбрать от 100 штук. Микрорайон, район, округ, <br />
                город − не проблема
              </p>
            </div>
          </div>
        </div>
        <div>
            
        </div>
        <p class="text-center my-5 text-lg">Оставьте заявку прямо сейчас, и уже через неделю вашу рекламу увидят все потенциальные клиенты!</p>
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