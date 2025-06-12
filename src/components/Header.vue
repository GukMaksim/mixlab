<script setup>
import { ref, watch, onMounted, onUnmounted } from 'vue';
import Button from '@/components/buttons/Button.vue';
import BurgerMenuBtn from '@/components/buttons/BurgerMenuBtn.vue';

const isMenuOpen = ref(false);
const currentPath = ref(window.location.pathname);

// Блокировка скролла при открытом меню
watch(isMenuOpen, (newValue) => {
  if (newValue) {
    document.body.style.overflow = 'hidden';
  } else {
    document.body.style.overflow = '';
  }
});

// Закрытие меню при изменении размера окна
const handleResize = () => {
  if (window.innerWidth > 768 && isMenuOpen.value) {
    isMenuOpen.value = false;
  }
};

// Закрытие меню при клике вне меню
const handleClickOutside = (event) => {
  const nav = document.querySelector('.nav');
  const burger = document.querySelector('.burger-menu-btn');

  if (isMenuOpen.value && nav && !nav.contains(event.target) && !burger?.contains(event.target)) {
    isMenuOpen.value = false;
  }
};

// Закрытие меню при нажатии Escape
const handleEscape = (event) => {
  if (event.key === 'Escape' && isMenuOpen.value) {
    isMenuOpen.value = false;
  }
};

onMounted(() => {
  window.addEventListener('resize', handleResize);
  document.addEventListener('click', handleClickOutside);
  document.addEventListener('keydown', handleEscape);
});

onUnmounted(() => {
  window.removeEventListener('resize', handleResize);
  document.removeEventListener('click', handleClickOutside);
  document.removeEventListener('keydown', handleEscape);
});

const menuItems = [
  { path: '/veterinarians', label: 'Veterinarians' },
  { path: '/how-it-works', label: 'How it works' },
  { path: '/about', label: 'About us' },
  { path: '/blog', label: 'Blog' },
  { path: '/shop', label: 'Shop' }
];
</script>

<template>
  <header class="header" role="banner">
    <div class="header-container">
      <BurgerMenuBtn :is-active="isMenuOpen" @click="isMenuOpen = !isMenuOpen" aria-label="Toggle menu"
        :aria-expanded="isMenuOpen" aria-controls="main-menu" class="burger-menu-btn" />

      <nav class="nav" :class="{ 'is-open': isMenuOpen }" role="navigation" aria-label="Main navigation">
        <ul class="nav__menu" id="main-menu">
          <li v-for="item in menuItems" :key="item.path">
            <a :href="item.path" class="nav__link" :class="{ 'is-active': currentPath === item.path }"
              @click="isMenuOpen = false" :aria-current="currentPath === item.path ? 'page' : undefined">
              {{ item.label }}
            </a>
          </li>
        </ul>
      </nav>

      <div class="logo">
        <a href="/" aria-label="Mixlab home">
          <img src="@/assets/Logo.png" alt="Mixlab logo" width="120" height="32" loading="eager" />
        </a>
      </div>

      <div class="header__actions">
        <a href="/login" class="login-link" aria-label="Veterinarian login">
          Veterinarian login
        </a>
        <Button text="Try Mixlab" aria-label="Try Mixlab service" variant="primary" size="small" />
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  padding: 1rem 0;
  background-color: var(--color-background, #ffffff);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
  transition: box-shadow 0.3s ease;
}

.header.scrolled {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

.header-container {
  max-width: 1440px;
  margin: 0 auto;
  padding: 0 1rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}

.nav__menu {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.logo {
  flex-shrink: 0;
}

.logo img {
  height: 32px;
  width: auto;
  transition: transform 0.3s ease;
}

.logo img:hover {
  transform: scale(1.05);
}

.header__actions {
  display: flex;
  align-items: center;
  gap: 1.5rem;
}

.login-link {
  text-decoration: none;
  color: var(--color-purple);
  font-weight: 500;
  font-size: 1rem;
  transition: color 0.3s;
  position: relative;
  padding: 0.5rem 0;
}

.login-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--color-purple);
  transition: width 0.3s;
}

.login-link:hover::after {
  width: 100%;
}

.nav__link {
  text-decoration: none;
  color: var(--color-text);
  font-weight: 500;
  transition: color 0.3s;
  position: relative;
  padding: 0.5rem 0;
}

.nav__link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--color-purple);
  transition: width 0.3s;
}

.nav__link:hover::after,
.nav__link.is-active::after {
  width: 100%;
}

.nav__link.is-active {
  color: var(--color-purple);
}

.nav__link:focus-visible {
  outline: 2px solid var(--color-purple);
  outline-offset: 4px;
  border-radius: 2px;
}

@media (max-width: 1024px) {
  .nav__menu {
    gap: 1.5rem;
  }

  .header-container {
    padding: 0 2rem;
  }
}

@media (max-width: 768px) {
  .header__actions {
    gap: 1rem;
  }

  .nav {
    position: fixed;
    top: 74px;
    left: 0;
    width: 100%;
    height: calc(100vh - 74px);
    background-color: var(--color-background, #ffffff);
    padding: 2rem;
    transform: translateX(-100%);
    transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
    z-index: 90;
    opacity: 0;
    visibility: hidden;
    box-shadow: 2px 0 4px rgba(0, 0, 0, 0.1);
    overflow-y: auto;
  }

  .nav.is-open {
    transform: translateX(0);
    opacity: 1;
    visibility: visible;
  }

  .nav__menu {
    flex-direction: column;
    align-items: center;
    gap: 1.5rem;
  }

  .nav__link {
    font-size: 1.25rem;
  }

  .header-container {
    padding: 0 1rem;
  }

  .burger-menu-btn {
    display: block;
  }
}

@media (max-width: 480px) {
  .header__actions {
    gap: 0.75rem;
  }

  .login-link {
    font-size: 0.875rem;
  }

  .nav {
    padding: 1.5rem;
  }
}
</style>