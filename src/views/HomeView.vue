<template>
  <main class="main">
    <div class="hero">
      <div class="">
        <swiper
          :loop="true"
          :speed="2000"
          :autoplay="{
            delay: 2000,
            disableOnInteraction: false,
          }"
          :pagination="pagination"
          :modules="modules"
          class="mySwiper"
        >
          <swiper-slide class="hero-fr">
            <div class="hero-fr-wrapper">
              <p class="hero-text">бренд</p>
              <p class="hero-title">american vintage</p>
              <p class="hero-text2">Смотреть коллекцию</p>
            </div>
          </swiper-slide>
          <swiper-slide class="hero-sc">
            <div class="hero-sc-wrapper">
              <p class="hero-text">бренд</p>
              <p class="hero-title">george gina lucy</p>
              <p class="hero-text2">Смотреть коллекцию</p>
            </div>
          </swiper-slide>
          <swiper-slide class="hero-th">
            <div class="hero-th-wrapper">
              <p class="hero-text">бренд</p>
              <p class="hero-title">deha</p>
              <p class="hero-text2">Смотреть коллекцию</p>
            </div>
          </swiper-slide>
          <swiper-slide class="hero-fo">
            <div class="hero-fo-wrapper">
              <p class="hero-text">бренд</p>
              <p class="hero-title">birkenstock</p>
              <p class="hero-text2">Смотреть коллекцию</p>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </div>

    <div class="arrival">
      <div class="arrival-left">
        <div class="container">
          <h1 class="arrival-left__title">new arrival</h1>
          <p class="arrival-left__text">
            Lorem ipsumLorem ipsumLorem ipsumLorem ipsumLorem ipLorem ipsumLorem
            ipLorem ipsumLorem ipsumLorem ipsumLorem ipsumLorem ipLorem
            ipsumLorem ip
          </p>
          <router-link class="arrival-left__link" to="/"
            >Смотреть коллекцию</router-link
          >
        </div>
      </div>

      <div class="arrival-right">
        <div class="arrival-right-item">
          <p class="arrival-right-item__text">
            Lorem ipsumLorem ipsumLorem ipsumLorem ipsumLorem ipLorem ipsumLorem
            ip
          </p>
        </div>
      </div>
    </div>

    <div class="popular">
      <div class="container">
        <h1 class="popular__title">Популярное</h1>
        <swiper
          class="popular-cards"
          :speed="2000"
          :autoplay="{
            delay: 2000,
            disableOnInteraction: false,
          }"
          :pagination="pagination"
          :navigation="true"
          :slides-per-view="4"
          :space-between="50"
          
        >
          <swiper-slide class="popular-cards-item" v-for="p in cat" :key="p.id">
            <img class="popular-cards-item__img" :src="p.images[0]" alt="jpg" />
            <section class="popular-cards-item-wrapper">
              <h2 class="popular-cards-item-wrapper__title">{{ p.title }}</h2>
              <p class="popular-cards-item-wrapper__text">Classic shoes</p>
              <div class="popular-cards-item-wrapper-coust">
                <p class="popular-cards-item-wrapper-coust__text">6100 UAH</p>
                <p class="popular-cards-item-wrapper-coust__text">3800 UAH</p>
              </div>
            </section>
          </swiper-slide>
        </swiper>
      </div>
    </div>
  </main>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";

import "swiper/css/pagination";
import 'swiper/css/navigation';

import { Autoplay, Pagination, Navigation } from "swiper";

import { ref, computed } from "vue";

const modules = [Pagination, Autoplay, Navigation];
const pagination = {
  clickable: true,
  renderBullet: function (index, className) {
    return '<span class="' + className + '">' + 0 + (index + 1) + "</span>";
  },
};

async function getProducts() {
  const res = await fetch("https://api.escuelajs.co/api/v1/products");
  const data = await res.json();
  products.value = data;
}
const cat = computed(() => {
  return products.value.filter((p) => p.category.id === 2);
});
const products = ref([]);
getProducts();
</script>
