<template>
  <header class="header">
    <!-- header nav section -->
    <nav class="header-nav">
      <div class="container">
        <router-link to="/" class="header-nav-logo">
          <img
            class="header-nav-logo__img"
            src="@/assets/images/svg/logo.svg"
            alt="logo"
          />
        </router-link>

        <div class="header-nav-categories">
          <button class="header-nav-categories__item">Женщины</button>
          <button class="header-nav-categories__item">Мужчины</button>
          <button class="header-nav-categories__item">
            <label for="search">поиск</label>
            <input type="search" id="search" />
          </button>
        </div>

        <ul class="header-nav-langs">
          <li class="header-nav-langs__item"><a href="#">Ru</a></li>
          <li class="header-nav-langs__item"><a href="#">ua</a></li>
          <li class="header-nav-langs__item"><a href="#">en</a></li>
        </ul>

        <div class="header-nav-options">
          <button class="header-nav-options-item">
            <img src="@/assets/images/svg/contacts.svg" alt="contacts" />
          </button>
          <button class="header-nav-options-item">
            <img src="@/assets/images/svg/heart.svg" alt="favourite" />
          </button>
          <button class="header-nav-options-item">
            <img src="@/assets/images/svg/basket.svg" alt="basket" />
          </button>
        </div>
      </div>
    </nav>
    <!-- header nav section end -->

    <!--  -->
  </header>
  <RouterView />
<div class="modal" v-if="openModal">

</div>
  <footer class="footer">
    <span class="footer-line"></span>
    <div class="container">
      <div class="footer-top">
        <div class="footer-top-wrapper">
          <h2 class="footer-top-wrapper__title">Будьте в курсе событий</h2>
          <form>
            <input type="search" id="footer-search" />
            <button type="submit" for="footer-search">
              <img src="@/assets/images/svg/footer-submit.svg" alt="submit" />
            </button>
          </form>
          <div class="footer-top-list">
            <router-link to="/" class="footer-top-list-item">О нас</router-link>
            <router-link to="/" class="footer-top-list-item"
              >Распространенные вопросы</router-link
            >
            <router-link to="/" class="footer-top-list-item">Бренды</router-link>
          </div>
        </div>
      </div>
    </div>
      <span class="footer-line"></span>
    <div class="footer-bottom">
      <h3 class="footer-bottom-text">Все права защищены © 2020 Allegria.com</h3>
      <h3 class="footer-bottom-text">Дизайн и разработка:</h3>
    </div>
  </footer>
</template>

<script setup>
  import { ref,computed } from 'vue';
2
</script>

<style lang="scss" scoped></style>
