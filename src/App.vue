<script setup>
import Header from './components/Header.vue'
import AdPlacement from './components/AdPlacement.vue'
import Reviews from './components/Reviews.vue'
import Required from './components/Required.vue'
import ContinuousSlider from './components/ContinuousSlider.vue'
import Benefits from './components/Benefits.vue'
import Stand from './components/Stand.vue'
import About from './components/About.vue'
import Price from './components/Price.vue'
import Footer from './components/Footer.vue'
import BackToTop from './components/BackToTop.vue'

</script>

<template>
<div class="app">
<div class="bg-white mx-0 h-screen rounded-xl shadow-xl mt-14">
<Header/>
<AdPlacement class="mt-10"/>
<Reviews class="mt-40 "/>

<img src="/public/img/main/7.png" alt="" class="mt-10">
<Required/>

<ContinuousSlider class="my-20"/>

<Benefits/>

<Stand/>

<BackToTop/>

<About/>

<Price/>

<Footer/>

</div>


</div>

</template>

<script>

export default {
  components: {
    BackToTop
  }
}
</script>