<script setup>
import { ref, watch } from 'vue';
import TheButton from '@/components/buttons/TheButton.vue';
import BurgerMenuBtn from '@/components/buttons/BurgerMenuBtn.vue';

const isMenuOpen = ref(false);

// Блокировка скролла при открытом меню
watch(isMenuOpen, (newValue) => {
  if (newValue) {
    document.body.style.overflow = 'hidden';
  } else {
    document.body.style.overflow = '';
  }
});
</script>

<template>
  <header class="header">
    <div class="container">
      <BurgerMenuBtn :is-active="isMenuOpen" @click="isMenuOpen = !isMenuOpen" />

      <nav class="nav" :class="{ 'is-open': isMenuOpen }">
        <ul class="nav__menu">
          <li><a href="#" class="nav__link" @click="isMenuOpen = false">Veterinarians</a></li>
          <li><a href="#" class="nav__link" @click="isMenuOpen = false">How it works</a></li>
          <li><a href="#" class="nav__link" @click="isMenuOpen = false">About us</a></li>
          <li><a href="#" class="nav__link" @click="isMenuOpen = false">Blog</a></li>
          <li><a href="#" class="nav__link" @click="isMenuOpen = false">Shop</a></li>
        </ul>
      </nav>

      <div class="logo">
        <img src="@/assets/logo.png" alt="Mixlab logo" />
      </div>
      <div class="header__actions">
        <a href="#" class="login-link">Veterinarian login</a>
        <TheButton :class="'button-header'" text="Try Mixlab" />
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  padding: 16px 0;
}

.nav__menu {
  display: flex;
  list-style: none;
  gap: 32px;
  margin: 0;
  padding: 0;
}

.logo img {
  height: 32px;
}

.header__actions {
  display: flex;
  align-items: center;
  gap: 24px;
}

.login-link {
  text-decoration: none;
  color: var(--color-purple);
  font-weight: 500;
  font-size: 16px;
  transition: color 0.3s;
}

.login-link:hover {
  color: var(--color-purple-hover);
}

.nav__link {
  text-decoration: none;
  color: var(--color-text);
  font-weight: 500;
  transition: color 0.3s;
}

.nav__link:hover {
  color: var(--color-purple-hover);
}

@media (max-width: 1024px) {
  .nav__menu {
    gap: 20px;
  }
}

@media (max-width: 768px) {
  .header__actions {
    gap: 16px;
  }

  .nav {
    position: fixed;
    top: 74px;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: white;
    padding: 80px 20px;
    transform: translateX(-100%);
    transition: transform 0.3s ease-in-out;
    z-index: 90;
    display: block;
    opacity: 0;
    visibility: hidden;
  }

  .nav.is-open {
    transform: translateX(0);
    opacity: 1;
    visibility: visible;
  }

  .nav__menu {
    flex-direction: column;
    align-items: center;
    gap: 24px;
  }

  .nav__link {
    font-size: 24px;
  }

  .header {
    position: relative;
    z-index: 100;
    background-color: white;
  }
}
</style>