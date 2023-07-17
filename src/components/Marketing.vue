<script setup>
import shapeImages from "../data/marketing-shape.js";
const marketing = 'src/assets/images/marketing/marketing.png'
const seoBg = 'src/assets/images/backgrounds/seo-bg.png'
</script>

<template>
  <!-- marketing -->
  <section class="section-lg seo" id="marketing">
    <div class="container">
      <div class="row">
        <div class="col-md-6">
          <div class="seo-image">
            <img class="img-fluid" :src="marketing" alt="form-img">
          </div>
        </div>
        <div class="col-md-5">
          <h2 class="section-title">A Complete Range Of SEO Marketing Services!</h2>
          <p>Far far away, behind the word mountains, far
            from the countries Vokalia and Consonantia.<br>
            There live the blind texts. Separated they
            live in Bookmarksgrove right at the coast of
            the Semantics, a large language ocean.
          </p>
        </div>
      </div>
    </div>
    <!-- background image -->
    <img class="img-fluid seo-bg" :src="seoBg" alt="seo-bg">
    <!-- background-shape -->
    <img v-for="(shape, index) in shapeImages" :key="index" :class="shape.animation" :src="shape.image" :alt="shape.alt">
  </section>
  <!-- /marketing -->
</template>

<style scoped>

</style>