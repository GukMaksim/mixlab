<script setup>
import TheHeader from '@/components/TheHeader.vue'
import TheHero from '@/components/TheHero.vue'
import TheExperience from '@/components/TheExperience.vue';
import HowItWorks from '@/components/HowItWorks.vue';
</script>

<template>
  <div class="app">
    <TheHeader />
    <main>
      <TheHero />
      <TheExperience />
      <HowItWorks />
    </main>
  </div>
</template>

<style scoped>
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

main {
  flex: 1;
}
</style>
