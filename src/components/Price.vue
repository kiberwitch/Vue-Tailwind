<template>


<header class="bg-red-800 text-white py-8 w-300 m-auto text-center mt-20 " id="price-section">
        <div class="container mx-auto px-4">
            <h1 class="text-3xl md:text-4xl font-bold mb-2">Прайс-лист на баннерную рекламу</h1>
            <p class="text-blue-100">Актуальные цены на [месяц, год]</p>
        </div>
    </header>

    <!-- Основной контент -->
    <main class="container mx-auto px-4 py-12">
        <!-- 1. Билборды -->
        <section class="mb-16">
            <h2 class="text-2xl font-bold mb-6 text-gray-800 border-b pb-2">1. Реклама на билбордах (3×6 м)</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Карточка 1 месяц -->
                <div class="price-card bg-white rounded-lg shadow-md overflow-hidden border border-gray-200">
                    <div class="bg-red-800 text-white py-4 px-6">
                        <h3 class="font-bold text-lg">1 месяц</h3>
                    </div>
                    <div class="p-6">
                        <p class="text-gray-600 mb-4">Стандартное размещение</p>
                        <div class="flex items-end mb-4">
                            <span class="text-3xl font-bold text-gray-800">25 000</span>
                            <span class="text-gray-500 ml-1">руб.</span>
                        </div>
                        <button class="w-full bg-red-800 hover:bg-red-600 text-white py-2 rounded transition">
                            Заказать
                        </button>
                    </div>
                </div>

                <!-- Карточка 3 месяца -->
                <div class="price-card bg-white rounded-lg shadow-md overflow-hidden border border-gray-200">
                    <div class="bg-red-800 text-white py-4 px-6">
                        <h3 class="font-bold text-lg">3 месяца</h3>
                    </div>
                    <div class="p-6">
                        <p class="text-gray-600 mb-4">Экономия 10%</p>
                        <div class="flex items-end mb-4">
                            <span class="text-3xl font-bold text-gray-800">65 000</span>
                            <span class="text-gray-500 ml-1">руб.</span>
                        </div>
                        <button class="w-full bg-red-800 hover:bg-red-700 text-white py-2 rounded transition">
                            Заказать
                        </button>
                    </div>
                </div>

                <!-- Остальные карточки аналогично -->
            </div>
        </section>

        <!-- 2. Суперсайты -->
        <section class="mb-16">
            <h2 class="text-2xl font-bold mb-6 text-gray-800 border-b pb-2">2. Суперсайты (5×15 м)</h2>
            <div class="grid md:grid-cols-3 gap-6">
                <!-- Карточки аналогично предыдущему блоку -->
            </div>
        </section>

        <!-- Дополнительные услуги -->
        <section class="mb-16">
            <h2 class="text-2xl font-bold mb-6 text-gray-800 border-b pb-2">Дополнительные услуги</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <div class="bg-white p-6 rounded-lg shadow border border-gray-200">
                    <div class="text-blue-500 mb-3">
                        <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 20 20">...</svg>
                    </div>
                    <h3 class="font-bold text-lg mb-2">Разработка дизайна</h3>
                    <p class="text-gray-600 mb-4">Профессиональный дизайн баннера</p>
                    <p class="text-xl font-semibold">от 5 000 руб.</p>
                </div>
                <!-- Остальные услуги -->
            </div>
        </section>

        <!-- Примечания -->
        <section class="bg-gray-50 border-l-4 border-red-800 p-6 rounded">
            <h3 class="font-bold text-lg mb-3">Примечания:</h3>
            <ul class="list-disc pl-5 space-y-2 text-gray-700">
                <li>Цены указаны для стандартных локаций</li>
                <li>Премиальные места обсуждаются индивидуально</li>
                <li>Скидки при размещении на нескольких площадках</li>
            </ul>
        </section>
    </main>


</template>


    <style>
        .price-card {
            transition: all 0.3s ease;
        }
        .price-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px -5px rgba(255, 0, 0, 0.1);
        }
    </style>

