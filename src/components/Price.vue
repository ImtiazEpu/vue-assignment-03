<script setup>
import { shapeImages, pricingData } from "../data/price.js";
</script>

<template>
  <section class="section-lg pb-0 pricing" id="pricing">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-title">Our Pricing</h2>
          <p class="mb-50">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu <br>
            fugiat nulla pariatur. Excepteur sint occaecat </p>
        </div>
        <div class="col-lg-10 mx-auto">
          <div class="row justify-content-center">
            <div v-for="(item, index) in pricingData" :key="index" class="col-md-6 col-lg-4 mb-5 mb-lg-0">
              <div :class="'rounded text-center pricing-table ' + item.tableClass">
                <h3>{{ item.title }}</h3>
                <h1><span>$</span>{{ item.price }}</h1>
                <p>{{ item.description }}</p>
                <a :href="item.buttonLink" class="btn pricing-btn px-2">{{ item.buttonText }}</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <img v-for="(shape, index) in shapeImages" :key="index" :class="shape.animation" :src="shape.image" :alt="shape.alt">
  </section>
</template>

<style scoped>

</style>