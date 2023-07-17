<script setup>
import backgroundShapes from "../data/shape.js";
const bgImage = 'background-image: url(src/assets/images/hero-area/banner-bg.png)'
const bannerImage = 'src/assets/images/hero-area/banner-img.png'
</script>

<template>
  <!-- hero area -->
  <section class="hero-section hero" data-background="" :style="bgImage">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center zindex-1">
          <h1 class="mb-3">Take Control of your<br>
            Project and Team</h1>
          <p class="mb-4">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum<br>
            dolore eu fugiat nulla pariatur.</p>
          <a href="#" class="btn btn-secondary btn-lg">explore us</a>
          <!-- banner image -->
          <img class="img-fluid w-100 banner-image" :src="bannerImage" alt="banner-img">
        </div>
      </div>
    </div>
    <!-- background shapes -->
    <div id="scene">
      <img v-for="(shape, index) in backgroundShapes" :key="index" :class="shape.animation" :src="shape.image" alt="">
    </div>
  </section>
  <!-- /hero-area -->
</template>

<style scoped>

</style>