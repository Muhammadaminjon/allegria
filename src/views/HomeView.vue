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
        <div class="popular-cards__wrapper">
          <swiper
            class="popular-cards"
            :autoplay="{
              delay: 2000,
              disableOnInteraction: false,
            }"
            pagination
            :navigation="true"
            :slides-per-view="4"
            :space-between="45"
            :modules="modules"
          >
            <swiper-slide
              class="popular-cards-item"
              v-for="p in cat"
              :key="p.id"
            >
              <img
                class="popular-cards-item__img"
                :src="p.images[0]"
                alt="jpg"
              />
              <section class="popular-cards-item-wrapper">
                <router-link
                  class="popular-cards-item-wrapper__title"
                  :to="{ name: 'product', params: { id: p.id } }"
                  >{{ p.title }}</router-link
                >
                <!-- <h2 class="popular-cards-item-wrapper__title">{{ p.title }}</h2> -->
                <p class="popular-cards-item-wrapper__text">
                  {{ p.category.name }}
                </p>
                <div class="popular-cards-item-wrapper-coust">
                  <p class="popular-cards-item-wrapper-coust__price"></p>
                  <p class="popular-cards-item-wrapper-coust__text">
                    ${{ p.price }}
                  </p>
                </div>
              </section>
            </swiper-slide>
          </swiper>
        </div>
      </div>
      <span class="popular__bottom">
        <img class="bottom-img" src="@/assets/images/svg/logo.svg" alt="logo" />
      </span>
    </div>

    <div class="about">
      <div class="about-wrappers">
        <div class="container">
          <div class="about-wrappers-wrapper">
            <section class="about-wrappers-wraper-item">
              <h2 class="about-wrappers-wraper-item__title">
                <span>О</span>нас
              </h2>
              <p class="about-wrappers-wraper-item__text">
                Lorem ipsumLorem ipsumLorem ipsumLorem ipsumLorem ipLorem
                ipsumLoreLorem ipsumLorem ipsumLorem ipsumLorem ipsumLorem
                ipLorem ipsumLorem ipsumLorem ipsumLorem ipsumLorem ipsumLorem
                ipsumLorem ipsumLorem ipsumipLorem ipsumLoremLorem ipsumLorem
                ipsumLorem ipsumLorem ipsumLorem ipLorem ipsumLorem ipsumLorem
                ipsumLorem
              </p>
            </section>

            <div class="about-wrappers-wrapper2">
              <img
                class="about-img"
                src="@/assets/images/jpg/about-img.jpg"
                alt="about-img"
              />
              <img
                class="about-icon"
                src="@/assets/images/svg/about-icon.svg"
                alt="about-icon"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";

import "swiper/css/pagination";
import "swiper/css/navigation";

import { Autoplay, Pagination, Navigation } from "swiper";

import { ref, computed } from "vue";

const modules = [Pagination, Autoplay, Navigation];
const pagination = {
  clickable: true,
  renderBullet: function (index, className) {
    return '<span class="' + className + '">' + 0 + (index + 1) + "</span>";
  },
};
const pagination2 = {
  clickable: true,
  width: 90,
  height: 90,
};

async function getProducts() {
  const res = await fetch("https://api.escuelajs.co/api/v1/products/");
  const data = await res.json();
  products.value = data;
}
const cat = computed(() => {
  return products.value.filter((p) => p.category.id === 4);
});
const products = ref([]);
getProducts();
</script>
