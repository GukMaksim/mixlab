<script setup>
import TheButton from '@/components/buttons/TheButton.vue';
</script>

<template>
  <section class="support">
    <div class="container">
      <div class="support__img-wrapper">
        <img class="support__img" src="@/assets/support.png" alt="support">
      </div>
      <div class="support__info-wrapper">
        <p class="support__suptitle">For Veterinarians</p>
        <h2 class="support__title">We're here to support you and your practice</h2>
        <p class="support__text">Mixlab offers a simple, fast, reliable (and fun) home delivery pharmacy service for
          your clients. No more delays, no more miscommunications, no more grumpy pets. It’s time to partner with a
          pharmacy that cares about customer experience as much as you do.</p>
        <TheButton text="Learn More" />
      </div>
    </div>
  </section>
</template>

<style scoped>
.support {
  background-color: #F6F3FA;
}

.support__img-wrapper,
.support__info-wrapper {
  width: 50%;
}

.support__suptitle {
  letter-spacing: 0.96px;
  text-transform: uppercase;
  color: #F7A500;
  font-weight: 700;
  margin-bottom: 8px;
}

.support__title {
  margin-bottom: 40px;
}

.support__text {
  margin-bottom: 48px;
}
</style>