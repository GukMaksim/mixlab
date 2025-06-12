<script setup>
defineProps({
  isActive: {
    type: Boolean,
    default: false
  }
});

defineEmits(['click']);
</script>

<template>
  <button class="burger-menu" :class="{ 'is-active': isActive }" @click="$emit('click')" type="button"
    :aria-expanded="isActive" :aria-label="isActive ? 'Close menu' : 'Open menu'">
    <span class="burger-menu__line" aria-hidden="true"></span>
    <span class="burger-menu__line" aria-hidden="true"></span>
    <span class="burger-menu__line" aria-hidden="true"></span>
  </button>
</template>

<style scoped>
.burger-menu {
  display: none;
  width: 2rem;
  height: 1.5rem;
  position: relative;
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  z-index: 100;
  transition: transform 0.3s ease;
}

.burger-menu:hover {
  transform: scale(1.1);
}

.burger-menu:focus-visible {
  outline: 2px solid var(--color-purple);
  outline-offset: 4px;
  border-radius: 4px;
}

.burger-menu__line {
  display: block;
  width: 100%;
  height: 2px;
  background-color: var(--color-text);
  position: absolute;
  left: 0;
  transition: transform 0.3s ease, opacity 0.3s ease, background-color 0.3s ease;
}

.burger-menu__line:nth-child(1) {
  top: 0;
}

.burger-menu__line:nth-child(2) {
  top: 50%;
  transform: translateY(-50%);
}

.burger-menu__line:nth-child(3) {
  bottom: 0;
}

/* Active state */
.burger-menu.is-active .burger-menu__line:nth-child(1) {
  transform: translateY(0.6875rem) rotate(45deg);
}

.burger-menu.is-active .burger-menu__line:nth-child(2) {
  opacity: 0;
  transform: translateX(-1rem);
}

.burger-menu.is-active .burger-menu__line:nth-child(3) {
  transform: translateY(-0.6875rem) rotate(-45deg);
}

/* Hover state */
.burger-menu:hover .burger-menu__line {
  background-color: var(--color-purple);
}

/* Active hover state */
.burger-menu.is-active:hover .burger-menu__line {
  background-color: var(--color-purple-dark);
}

@media (max-width: 768px) {
  .burger-menu {
    display: block;
  }
}

@media (max-width: 480px) {
  .burger-menu {
    width: 1.75rem;
    height: 1.25rem;
  }

  .burger-menu.is-active .burger-menu__line:nth-child(1) {
    transform: translateY(0.5625rem) rotate(45deg);
  }

  .burger-menu.is-active .burger-menu__line:nth-child(3) {
    transform: translateY(-0.5625rem) rotate(-45deg);
  }
}
</style>