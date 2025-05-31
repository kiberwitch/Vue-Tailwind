<template>
    <footer class="bg-red-900 text-white py-12  " id="contacts-section">
    <div class="container  px-4 h-100">
        <div class="grid md:grid-cols-2 gap-8 items-center">
            <!-- Левая колонка - Карта -->
            <div class="h-96 rounded-lg overflow-hidden shadow-xl">
                <iframe src="https://yandex.ru/map-widget/v1/?um=constructor%3A4ca714cb7299ede711dd182f1e21c72e2394e510a0359435f9cbb7311575c77c&amp;source=constructor" width="800" height="400" frameborder="0"></iframe>
            </div>

            <!-- Правая колонка - Контакты -->
            <div class="pl-0 md:pl-8">
                <h2 class="text-2xl font-bold mb-6">Контакты</h2>
                
                <div class="space-y-6">
                    <div class="flex items-start">
                        <div class="bg-red-600 p-2 rounded-full mr-4">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                            </svg>
                        </div>
                        <div>
                            <h3 class="font-bold text-lg mb-1">Адрес</h3>
                            <p class="text-gray-300">г. Москва, ул. Рекламная, 15, офис 42</p>
                        </div>
                    </div>

                    <div class="flex items-start">
                        <div class="bg-red-600 p-2 rounded-full mr-4">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                            </svg>
                        </div>
                        <div>
                            <h3 class="font-bold text-lg mb-1">Телефон</h3>
                            <p class="text-gray-300">+7 (495) 123-45-67</p>
                            <p class="text-gray-300">+7 (800) 765-43-21</p>
                        </div>
                    </div>

                    <div class="flex items-start">
                        <div class="bg-red-600 p-2 rounded-full mr-4">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                            </svg>
                        </div>
                        <div>
                            <h3 class="font-bold text-lg mb-1">Email</h3>
                            <p class="text-gray-300">info@reklama-na-stendah.ru</p>
                            <p class="text-gray-300">sales@reklama-na-stendah.ru</p>
                        </div>
                    </div>

                    <div class="flex items-start">
                        <div class="bg-red-600 p-2 rounded-full mr-4">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/>
                            </svg>
                        </div>
                        <div>
                            <h3 class="font-bold text-lg mb-1">Режим работы</h3>
                            <p class="text-gray-300">Пн-Пт: 9:00 - 18:00</p>
                            <p class="text-gray-300">Сб-Вс: выходной</p>
                        </div>
                    </div>
                </div>

             
            </div>
        </div>
    </div>
</footer>
</template>