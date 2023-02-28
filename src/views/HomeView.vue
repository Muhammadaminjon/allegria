<template>
  <div class="hero">
    <div class="">
      <swiper :pagination="pagination" :modules="modules" class="mySwiper">
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
</template>
  <script>
    import { Swiper, SwiperSlide } from 'swiper/vue';
  
    import 'swiper/css';
  
    import 'swiper/css/pagination';
  
  
    import { Pagination } from 'swiper';
  
    export default {
      components: {
        Swiper,
        SwiperSlide,
      },
      setup() {
        return {
          pagination: {
            clickable: true,
            renderBullet: function (index, className) {
              return '<span class="' + className + '">' + 0 + (index+1) + '</span>';
            },
          },
          modules: [Pagination],
        };
      },
    };
  </script>