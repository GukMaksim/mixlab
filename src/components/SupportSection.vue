<script setup>
import Button from '@/components/buttons/Button.vue';
</script>

<template>
  <section class="support" aria-labelledby="support-title">
    <div class="container">
      <div class="support__img-wrapper" role="img" aria-label="Veterinarian with happy pet">
        <img class="support__img" src="@/assets/support.png" alt="Veterinarian with happy pet" width="600" height="400"
          loading="lazy">
      </div>
      <div class="support__info-wrapper">
        <p class="support__suptitle" role="doc-subtitle">
          For Veterinarians
        </p>
        <h2 id="support-title" class="support__title">
          We're here to support you and your practice
        </h2>
        <p class="support__text">
          Mixlab offers a simple, fast, reliable (and fun) home delivery pharmacy service for your clients.
          No more delays, no more miscommunications, no more grumpy pets. It's time to partner with a
          pharmacy that cares about customer experience as much as you do.
        </p>
        <Button text="Learn More" class="support__button" aria-label="Learn more about our veterinary support program"
          variant="primary" size="large" />
      </div>
    </div>
  </section>
</template>

<style scoped>
.support {
  background-color: var(--color-background-purple, #F6F3FA);
  padding: 4rem 0;
}

.container {
  max-width: 90rem;
  margin: 0 auto;
  padding: 0 1rem;
  display: flex;
  align-items: center;
  gap: 4rem;
}

.support__img-wrapper,
.support__info-wrapper {
  width: 50%;
}

.support__img {
  width: 100%;
  height: auto;
}

.support__suptitle {
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: var(--color-accent, #F7A500);
  font-weight: 700;
  font-size: 0.875rem;
  margin-bottom: 0.5rem;
}

.support__title {
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  line-height: 1.2;
  margin-bottom: 2rem;
  color: var(--color-text-dark, #1A1A1A);
  font-weight: 700;
}

.support__text {
  font-size: clamp(1rem, 1.5vw, 1.125rem);
  line-height: 1.5;
  color: var(--color-text, #4A4A4A);
  margin-bottom: 2rem;
}

.support__button {
  margin-top: 1rem;
}

@media (max-width: 1024px) {
  .container {
    gap: 2rem;
  }
}

@media (max-width: 768px) {
  .support {
    padding: 3rem 0;
  }

  .container {
    flex-direction: column;
    gap: 3rem;
  }

  .support__img-wrapper,
  .support__info-wrapper {
    width: 100%;
  }

  .support__img-wrapper {
    order: -1;
  }

  .support__title {
    text-align: center;
  }

  .support__text {
    text-align: center;
  }

  .support__button {
    margin: 1rem auto 0;
  }
}

@media (max-width: 480px) {
  .support {
    padding: 2rem 0;
  }

  .container {
    gap: 2rem;
  }

  .support__img {
    border-radius: 0.5rem;
  }
}

@media (prefers-reduced-motion: reduce) {
  .support__img {
    transition: none;
  }

  .support__img:hover {
    transform: none;
  }
}
</style>