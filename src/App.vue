<script setup>

import { ref } from 'vue';

const showImage = ref(0)

"./assets/logo.png"

const images = ref(["./src/assets/img/1.jpg",
"./src/assets/img/2.jpeg",
"./src/assets/img/3.jpg",
"./src/assets/img/4.jpg",
"./src/assets/img/5.jpeg",
"./src/assets/img/6.jpeg",
"./src/assets/img/7.jpeg",
"./src/assets/img/8.jpg"

])

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Image Carousel</h1>
  <div id="carouselExampleIndicators" class="carousel slide " data-ride="carousel">
  <ol class="carousel-indicators">
    <template v-for="(image,index) in images" :key="index">
      <li @click="showImage=index" v-if="index==showImage" class="active"></li>
      <li @click="showImage=index" v-else></li>
    </template>
    
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active" v-for="(image,index) in images" v-show="showImage==index" :key="index">
      <img class="d-block w-100 h-80" :src="image" alt="First slide">
    </div>
  </div>
  <a @click="showImage--" v-show="showImage>0" class="carousel-control-prev" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a @click="showImage++" v-show="showImage<(images.length-1)" class="carousel-control-next" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
  </section>
</template>

<style scoped></style>