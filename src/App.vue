<script setup>
import TheHeader from '@/components/TheHeader.vue'
import TheHero from '@/components/TheHero.vue'
import TheExperience from '@/components/TheExperience.vue';
import HowItWorks from '@/components/HowItWorks.vue';
import TheSupport from '@/components/TheSupport.vue';
import TheTestimonials from '@/components/TheTestimonials.vue';
</script>

<template>
  <div class="app">
    <TheHeader />
    <main>
      <TheHero />
      <TheExperience />
      <HowItWorks />
      <TheSupport />
      <TheTestimonials />
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
