<script setup>
import { teamMembers } from "../data/team.js";
import { shapeImages } from "../data/team.js";
import { Carousel, Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';

const teamBg = 'src/assets/images/backgrounds/team-bg.png';
</script>

<template>
  <section class="section-lg team" id="team">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-title">Our Team</h2>
          <p class="mb-100">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu<br>
            fugiat nulla pariatur. Excepteur sint occaecat </p>
        </div>
      </div>
      <div class="col-12">
        <Carousel class="team-slider"
                  :itemsToShow="3"
                  :itemsToScroll="1"
                  :controls="true"
                  :autoplay="true"
                  :autoplayInterval="5000">
          <Slide v-for="(member, index) in teamMembers" :key="index" class="team-member">
            <div class="d-flex mb-4">
              <div class="mr-3">
                <img class="rounded-circle img-fluid" :src="member.image" :alt="'team-member-' + index">
              </div>
              <div class="align-self-center">
                <h4>{{ member.name }}</h4>
                <h6 class="text-color">{{ member.role }}</h6>
              </div>
            </div>
            <p>{{ member.description }}</p>
          </Slide>
        </Carousel>
      </div>
    </div>
    <img class="img-fluid team-bg" :src="teamBg" alt="team-bg">
    <img v-for="(shape, index) in shapeImages" :key="index" :class="shape.animation" :src="shape.image" :alt="shape.alt">
  </section>
</template>

<style scoped>
.carousel{
  text-align: left;
}
.carousel__viewport {
  overflow: visible !important;
  width: 100%;
}
.carousel__slide {
  flex-direction: column;
  align-items: flex-start;
}
.carousel__track{
  max-width: 94%;
}
</style>