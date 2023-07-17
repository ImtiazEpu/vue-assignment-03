<script setup>
import menuItem from "../data/menuItem.js";
import {socialItems} from "../data/footer.js";

const logoUrl = 'src/assets/images/logo.png';
const homeLink = '/';
const footerBackground = 'background-image: url(src/assets/images/backgrounds/footer-bg.png)';

const scrollToElement = (elementId) => {
  event.preventDefault();
  const element = document.getElementById(elementId);
  element.scrollIntoView({ behavior: 'smooth' });
};
</script>


<!-- footer -->
<template>
  <footer class="footer-section footer" :style="footerBackground">
    <div class="container">
      <div class="row">
        <div class="col-lg-4 text-center text-lg-left mb-4 mb-lg-0">
          <!-- logo -->
          <a :href="homeLink">
            <img class="img-fluid" :src="logoUrl" alt="logo">
          </a>
        </div>
        <!-- footer menu -->
        <nav class="col-lg-8 align-self-center mb-5">
          <ul class="list-inline text-lg-right text-center footer-menu">
            <li class="list-inline-item" v-for="(item, index) in menuItem" :key="index" :class="{active: item.active}">
              <a href="" @click="scrollToElement(item.href)">{{ item.name }}</a>
            </li>
          </ul>
        </nav>
        <!-- footer social icon -->
        <nav class="col-12">
          <ul class="list-inline text-lg-right text-center social-icon">
            <li class="list-inline-item" v-for="(item, index) in socialItems" :key="index">
              <a :href="item.url"><i :class="item.iconClass"></i></a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </footer>
</template>
<!-- /footer -->

<style scoped>

</style>