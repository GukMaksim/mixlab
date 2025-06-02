<script setup>
defineProps({
  text: {
    type: String,
    required: true
  },
  href: {
    type: String,
    default: '#'
  }
});
</script>

<template>
  <a :href="href" class="button">{{ text }}</a>
</template>

<style scoped>
.button {
  background: var(--color-purple);
  color: white;
  border: none;
  padding: 16px 39px;
  border-radius: 24px;
  font-weight: 700;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
  text-decoration: none;
}

.button-header {
  padding: 8px 41px;
  font-size: 14px;
}

.button:hover {
  background: var(--color-purple-hover);
}
</style>