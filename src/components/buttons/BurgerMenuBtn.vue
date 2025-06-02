<script setup>
import { ref } from 'vue';

const isMenuOpen = ref(false);
</script>

<template>
  <button class="burger-menu">
    <span></span>
    <span></span>
    <span></span>
  </button>
</template>

<style scoped>
.burger-menu {
  display: none;
  width: 30px;
  height: 24px;
  position: relative;
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  z-index: 100;
}

.burger-menu span {
  display: block;
  width: 100%;
  height: 2px;
  background-color: var(--color-text);
  position: absolute;
  left: 0;
  transition: transform 0.3s, opacity 0.3s;
}

.burger-menu span:nth-child(1) {
  top: 0;
}

.burger-menu span:nth-child(2) {
  top: 50%;
  transform: translateY(-50%);
}

.burger-menu span:nth-child(3) {
  bottom: 0;
}

.burger-menu.is-active span:nth-child(1) {
  transform: translateY(11px) rotate(45deg);
}

.burger-menu.is-active span:nth-child(2) {
  opacity: 0;
}

.burger-menu.is-active span:nth-child(3) {
  transform: translateY(-11px) rotate(-45deg);
}

@media (max-width: 768px) {
  .burger-menu {
    display: block;
  }
}
</style>