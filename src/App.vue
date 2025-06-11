<script setup>
import Header from '@/components/Header.vue'
import HeroSection from '@/components/HeroSection.vue'
import ExperienceSection from '@/components/ExperienceSection.vue';
import HowItWorksSection from '@/components/HowItWorksSection.vue';
import SupportSection from '@/components/SupportSection.vue';
import TestimonialsSection from '@/components/TestimonialsSection.vue';
import ArticlesSection from './components/ArticlesSection.vue';
</script>

<template>
  <div class="app">
    <Header />
    <main>
      <HeroSection />
      <ExperienceSection />
      <HowItWorksSection />
      <SupportSection />
      <TestimonialsSection />
      <ArticlesSection />
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
