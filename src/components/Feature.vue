<script setup>
import featureItems from "../data/features.js";
const featureBg_1 = 'src/assets/images/background-shape/feature-bg-1.png'
const featureBg_2 = 'src/assets/images/background-shape/feature-bg-2.png'

const scrollToElement = (elementId) => {
  event.preventDefault();
  const element = document.getElementById(elementId);
  element.scrollIntoView({ behavior: 'smooth' });
};
</script>

<template>
  <section class="section feature mb-0" id="feature">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-title">Awesome Features</h2>
          <p class="mb-100">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.<br>Excepteur sint occaecat cupidatat non proident</p>
        </div>
        <!-- feature items loop -->
        <div v-for="(item, index) in featureItems" :key="index" class="col-md-6 mb-80">
          <div class="d-flex feature-item">
            <div>
              <i class="feature-icon mr-4" :class="item.iconClass"></i>
            </div>
            <div>
              <h4>{{ item.title }}</h4>
              <p>{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <img class="feature-bg-1 up-down-animation" :src="featureBg_1" alt="bg-shape">
    <img class="feature-bg-2 left-right-animation" :src="featureBg_2" alt="bg-shape">
  </section>
</template>

<style scoped>

</style>