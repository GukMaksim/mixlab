<script setup>
import Button from '@/components/buttons/Button.vue';
</script>

<template>
  <section class="hero" aria-labelledby="hero-title">
    <div class="hero__background">
      <img class="hero__img-left" src="@/assets/hero-img-left.png" alt="Decorative element" width="200" height="200"
        loading="lazy">
      <img class="hero__img-right" src="@/assets/hero-img-right.png" alt="Decorative element" width="200" height="200"
        loading="lazy">
      <img class="hero__img-center" src="@/assets/hero-img-center.png" alt="Decorative element" width="350" height="350"
        loading="lazy">
    </div>

    <div class="hero__content">
      <h1 id="hero-title" class="hero__title">
        The pet pharmacy humans are jealous of.
      </h1>

      <p class="hero__subtitle">
        5 stars on
        <a href="#" class="hero__link" aria-label="Read our reviews on Yelp">Yelp</a>,
        <a href="#" class="hero__link" aria-label="Read our reviews on Google">Google</a> and
        <a href="#" class="hero__link" aria-label="Read our reviews on Facebook">Facebook</a>
        because your best friend deserves only the best in pet care.
      </p>

      <Button text="Try Mixlab" class="hero__button" aria-label="Start using Mixlab service" variant="primary"
        size="large" />
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 40.625rem;
  position: relative;
  text-align: center;
  padding: 4rem 1rem;
  background-color: var(--color-background-light, #FEF7E5);
  overflow: hidden;
}

.hero__background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.hero__img-left,
.hero__img-right,
.hero__img-center {
  position: absolute;
  width: auto;
  height: auto;
  transition: transform 0.3s ease;
}

.hero__img-left {
  top: 0;
  left: 0;
  max-width: 12.5rem;
}

.hero__img-right {
  top: 0;
  right: 0;
  max-width: 12.5rem;
}

.hero__img-center {
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  max-width: 21.875rem;
}

.hero__content {
  position: relative;
  z-index: 1;
  max-width: 50rem;
  margin: 0 auto;
  padding: 0 1rem;
}

.hero__title {
  font-size: clamp(2rem, 5vw, 3.5rem);
  line-height: 1.2;
  margin: 0 auto;
  max-width: 38rem;
  color: var(--color-text-dark, #1A1A1A);
  font-weight: 700;
}

.hero__subtitle {
  max-width: 30.625rem;
  margin: 2rem auto;
  font-size: clamp(1rem, 2vw, 1.25rem);
  line-height: 1.4;
  color: var(--color-text, #4A4A4A);
}

.hero__link {
  color: var(--color-purple);
  text-decoration: none;
  transition: color 0.3s ease;
  position: relative;
  font-weight: 500;
}

.hero__link::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 1px;
  background-color: var(--color-purple);
  transition: width 0.3s ease;
}

.hero__link:hover {
  color: var(--color-purple-hover);
}

.hero__link:hover::after {
  width: 100%;
}

.hero__link:focus-visible {
  outline: 2px solid var(--color-purple);
  outline-offset: 4px;
  border-radius: 2px;
}

.hero__button {
  margin-top: 2rem;
}

@media (max-width: 1024px) {
  .hero {
    min-height: 35rem;
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 3rem 1rem;
    min-height: 30rem;
  }

  .hero__img-left,
  .hero__img-right {
    max-width: 9.375rem;
  }

  .hero__img-center {
    max-width: 15.625rem;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 2rem 1rem;
    min-height: 25rem;
  }

  .hero__img-left,
  .hero__img-right {
    max-width: 6.25rem;
  }

  .hero__img-center {
    max-width: 12.5rem;
  }

  .hero__content {
    padding: 0;
  }
}

@media (prefers-reduced-motion: reduce) {

  .hero__img-left,
  .hero__img-right,
  .hero__img-center,
  .hero__link::after {
    transition: none;
  }
}
</style>