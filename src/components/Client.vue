<script setup>
import clientLogos from "../data/client.js";

import { Carousel, Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';

const responsive = [
  {
    breakpoint: 1024,
    itemsToShow: 3,
    itemsToSlide: 1
  },
  {
    breakpoint: 600,
    itemsToShow: 3,
    itemsToSlide: 1
  },
  {
    breakpoint: 480,
    itemsToShow: 2,
    itemsToSlide: 1
  },
  {
    breakpoint: 400,
    itemsToShow: 1,
    itemsToSlide: 1
  }
]
</script>

<template>
  <section class="section">
    <div class="container">
      <Carousel class="client-logo-slider align-self-center"
                :itemsToShow="5"
                :itemsToSlide="1"
                :autoplay="true"
                :interval="1000"
                :responsive="responsive"
                :hideArrows="true"
                :hidePaginationDots="true"
                :wrapAround ="true"
                :transition="1000">

        <Slide v-for="(logo, index) in clientLogos" :key="index">
          <span href="" class="text-center d-block outline-0 p-5">
            <img class="d-unset img-fluid" :src="logo" alt="client-logo">
          </span>
        </Slide>
      </Carousel>
    </div>
  </section>
</template>

<style scoped>

</style>