<script setup>
import {serviceItems} from "../data/services.js";
import {shapeImages} from "../data/services.js";
const serviceImage = '/src/assets/images/service/service.png';
const serviceBg = '/src/assets/images/backgrounds/service-bg.png';
</script>

<template>
  <section class="section-lg service" id="service">
    <div class="container">
      <div class="row justify-content-between">
        <div class="col-md-5 order-2 order-md-1">
          <h2 class="section-title">Powerful Layout From Top To Bottom</h2>
          <p class="mb-4">Far far away, behind the word mountains,
            far from the countries Vokalia and Consonantia,
            there live the blind texts. Separated they
            live in Bookmarksgrove right at the coast of the
            Semantics, a large language ocean.</p>
          <ul class="pl-0 service-list">
            <li v-for="(item, index) in serviceItems" :key="index">
              <i :class="item.iconClass"></i>{{ item.text }}
            </li>
          </ul>
        </div>
        <div class="col-md-7 order-1 order-md-2">
          <img class="img-fluid layer-3" :src="serviceImage" alt="service">
        </div>
      </div>
    </div>
    <img class="img-fluid service-bg" :src="serviceBg" alt="service-bg">
    <img v-for="(shape, index) in shapeImages" :key="index" :class="shape.animation" :src="shape.image" :alt="shape.alt">
  </section>
</template>

<style scoped>

</style>