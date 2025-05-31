<template>
    <div class="flex flex-col p-5">
      <!-- Заголовок по центру -->
      <h1 class="m-auto text-4xl md:text-5xl uppercase font-black text-center mb-8">
        Почему стоит <span class="text-red-800">выбрать стенды?</span>
      </h1>
      
      <!-- Две колонки под заголовком -->
      <div class="flex flex-col md:flex-row gap-8 ">
        <!-- Левая колонка - преимущества -->
        <div class="flex-1 flex flex-col gap-5">
            <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Попадание в зону «СВОЙ»
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5  w-120  text-gray-500">
        Ваше предложение проникает на личную <br />
        территорию человека, в его дом;
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Высокая лояльность жителей 
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5 w-120 text-gray-500">
        Реклама размещается на информационных стендах <br>
        вместе с социально−значимой информацией города;
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Невозможно не заметить
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5  w-120  text-gray-500" >
        Реклама размещается на уровне глаз <br>
        и на расстоянии вытянутой руки;
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Максимальный охват жилого фонда
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5  w-120  text-gray-500">
        Рекламу видят 100% жителей города Москвы;
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Вся ваша целевая аудитория
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5  w-120  text-gray-500">
        От обычных домов до элитных жилых комплексов;
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Возможность отложенного решения
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5  w-120  text-gray-500">
        Можно снова обратиться к рекламе, уточнить подробности,
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer" >
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Реклама в шаговой доступности
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5  w-120  text-gray-500">
        Человек интересуется тем, что предлагают лично для него, <br>
        что он может получить в своем районе;
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Полностью легальное размещение
      </h2>
      <p class="border-2 border-red-600 p-2  w-120  text-gray-500">
        На основе конкурсов, проведенных Правительством г.Москвы;
      </p>
    </div>
    <div class="relative transition duration-200 hover:scale-105 cursor-pointer">
      <h2 class="absolute -top-3 left-4 bg-white px-2 text-lg font-medium uppercase">
        Высокое качество обслуживания
      </h2>
      <p class="border-2 border-red-600 p-2 pt-5  w-120  text-gray-500">
        Обеспечивается постоянный мониторинг состояния <br>
        конструкций, подтверждаемый фотоотчетом.
      </p>
    </div>
        </div>
        
        <!-- Правая колонка - изображение и форма -->
        <div class="flex-1 flex flex-col gap-5">
          <img 
            src="/public/img/main/8.png" 
            alt="Пример стенда" 
            class="w-100 h-auto object-cover rounded-lg shadow-lg m-auto transition duration-200 hover:scale-105 cursor-pointer"
          >
          
          <div class="border-2 border-gray-200 bg-white p-6 rounded-lg w-120 m-auto mt-30 ">
            <!-- Форма (как в вашем оригинальном коде) -->
            <div class="flex flex-col text-center ">
              <p class="text-sm md:text-base">
                Оформите заявку прямо сейчас
                <br />
                и получите
                <span class="text-red-400">
                  гарантированную скидку <br />
                  5% </span
                >на первое размещение <br />
                вашей рекламы!
              </p>
  
              <input
                type="tel"
                placeholder="+7 (___) ___-__-__"
                class="w-full m-auto mt-4 p-3 border rounded-lg focus:ring-2 focus:ring-red-500 focus:border-transparent"
                pattern="\+7\s\(\d{3}\)\s\d{3}-\d{2}-\d{2}"
              />
  
              <button
                @click="openPopup"
                class="m-auto border rounded-3xl w-full mt-4 py-3 uppercase text-white bg-red-800 hover:bg-red-900 transition duration-200 cursor-pointer text-sm md:text-base"
              >
                Оформить заявку
              </button>
            </div>
          </div>
        </div>
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
  </template>
  

  
<script setup>
import { ref } from 'vue'
import Popup from './Popup.vue'

const popupRef = ref(null)

const openPopup = () => {
  popupRef.value?.open()
}
</script>