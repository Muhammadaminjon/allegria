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
  </template>
  
  <script></script>
  
  <style lang="scss" scoped></style>
  