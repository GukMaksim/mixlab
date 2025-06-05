<script setup>
import TheButton from '@/components/buttons/TheButton.vue';
</script>

<template>
  <section class="hero">
    <img class="hero__img-left" src="@/assets/hero-img-left.png" alt="Декоративное изображение слева">
    <img class="hero__img-right" src="@/assets/hero-img-right.png" alt="Декоративное изображение справа">
    <img class="hero__img-center" src="@/assets/hero-img-center.png" alt="Декоративное изображение в центре">
    <h1 class="hero__title">The pet pharmacy humans are jealous of.</h1>
    <p class="hero__subtitle">5 stars on <a href="#">Yelp</a>, <a href="#">Google</a> and <a href="#">Facebook</a>
      because your best friend deserves only the best in pet care.</p>
    <TheButton text="Try Mixlab" />
    </section>
</template>

<style scoped>
.hero {
  height: 650px;
  position: relative;
  text-align: center;
  padding: 100px 20px;
  background-color: #FEF7E5;
}

.hero__img-left {
  position: absolute;
  top: 0;
  left: 0;
}

.hero__img-right {
  position: absolute;
  top: 0;
  right: 0;
}

.hero__img-center {
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 50%;
  max-width: 350px;
}

.hero__title {
  position: relative;
  z-index: 1;
  font-size: 55px;
  max-width: 565px;
  margin: 0 auto;
  line-height: 67px;
}

.hero__subtitle {
  position: relative;
  z-index: 1;
  max-width: 490px;
  margin: 0 auto;
  font-size: 20px;
  line-height: 28px;
  padding-top: 32px;
  padding-bottom: 48px;
}

.button {
  z-index: 1;
  position: relative;
}
</style>