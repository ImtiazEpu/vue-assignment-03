<script setup>
import navItems from "../data/menuItem.js";
const homeLink = '/';
const tryFreeLink = '#';
const logo = 'src/assets/images/logo.png'

import {ref, onMounted, onBeforeUnmount} from 'vue';

const scrollToElement = (elementId) => {
  event.preventDefault();
  const element = document.getElementById(elementId);
  element.scrollIntoView({ behavior: 'smooth' });
};

const isNavBg = ref(false);

const handleScroll = () => {
  isNavBg.value = window.scrollY > 100;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <!-- navigation -->
  <section class="fixed-top navigation" :class="{'navigation': true, 'nav-bg': isNavBg}">
    <div class="container">
      <nav class="navbar navbar-expand-lg navbar-light">
        <a class="navbar-brand" :href="homeLink"><img :src="logo" alt="logo"></a>
        <button class="navbar-toggler border-0" type="button" data-toggle="collapse" data-target="#navbar"
                aria-controls="navbar"
                aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <!-- navbar -->
        <div class="collapse navbar-collapse text-center" id="navbar">
          <ul class="navbar-nav ml-auto">
            <li class="nav-item" v-for="(navItem, index) in navItems" :key="index">
              <a class="nav-link page-scroll" href="#" @click="scrollToElement(navItem.href)">{{ navItem.name }}</a>
            </li>
          </ul>
          <a :href="tryFreeLink" class="btn btn-primary ml-lg-3 primary-shadow">Try Free</a>
        </div>
      </nav>
    </div>
  </section>
  <!-- /navigation -->
</template>

<style scoped>

</style>