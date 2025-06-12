<script setup>
import { onMounted } from 'vue';
import Header from '@/components/Header.vue'
import HeroSection from '@/components/HeroSection.vue'
import ExperienceSection from '@/components/ExperienceSection.vue';
import HowItWorksSection from '@/components/HowItWorksSection.vue';
import SupportSection from '@/components/SupportSection.vue';
import TestimonialsSection from '@/components/TestimonialsSection.vue';
import ArticlesSection from './components/ArticlesSection.vue';
import Footer from './components/Footer.vue';

// SEO мета-теги
onMounted(() => {
  document.title = 'MixLab - Veterinary Pharmacy & Pet Care';
  const metaDescription = document.createElement('meta');
  metaDescription.name = 'description';
  metaDescription.content = 'MixLab - Your trusted veterinary pharmacy and pet care solution. Get prescription medications delivered to your door.';
  document.head.appendChild(metaDescription);
});
</script>

<template>
  <div class="app" role="application">
    <Header />
    <main role="main">
      <HeroSection />
      <ExperienceSection />
      <HowItWorksSection />
      <SupportSection />
      <TestimonialsSection />
      <ArticlesSection />
    </main>
    <Footer />
  </div>
</template>

<style scoped>
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background-color: var(--color-background, #ffffff);
}
</style>
