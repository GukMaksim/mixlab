<script setup>
const experienceItems = [
  {
    title: 'Patients first, always',
    text: 'We know how stressful it can be when your pet needs meds. That\'s why we offer free next-day delivery and even do same-day in NYC and LA. We got you.',
    icon: '🐾',
    id: 'patients-first'
  },
  {
    title: 'Tailored care',
    text: 'We\'ll work with you and your veterinarian to find the very best solution for your pet. With our custom compounded options, we can change the dosage, flavor and form. We even have a flavor guarantee with over 40 options!',
    note: 'P.S. Everyone seems to love the chicken-flavored chew treats!',
    icon: '🎯',
    id: 'tailored-care'
  },
  {
    title: 'Support, 7 days a week',
    text: 'You\'re not alone. Text, call, or email us 7 days a week—we\'ll answer and do our best to sprinkle in a bit of sunshine.',
    icon: '☀️',
    id: 'support'
  }
];
</script>

<template>
  <section class="experience" aria-labelledby="experience-title">
    <div class="container">
      <div class="experience__inner experience__inner-left">
        <h2 id="experience-title" class="experience__title">
          We couldn't find a pharmacy experience worthy of our best buds— so we created one.
        </h2>
        <img src="@/assets/experience-img.png" alt="Happy pet owner with their pet" class="experience__img" width="280"
          height="280" loading="lazy">
      </div>

      <div class="experience__inner experience__inner-right" role="list" aria-label="Our key features">
        <div v-for="item in experienceItems" :key="item.id" class="experience__item" role="listitem">
          <h3 :id="item.id" class="experience__subtitle">
            <span class="experience__icon" aria-hidden="true" role="img" :aria-label="`${item.title} icon`">
              {{ item.icon }}
            </span>
            {{ item.title }}
          </h3>
          <p class="experience__text">{{ item.text }}</p>
          <p v-if="item.note" class="experience__note" aria-label="Additional note">
            {{ item.note }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience {
  padding: 4rem 1rem;
  background-color: var(--color-background, #ffffff);
}

.container {
  max-width: 90rem;
  margin: 0 auto;
  padding: 0 1rem;
  display: flex;
  gap: 4rem;
}

.experience__inner {
  width: 50%;
  text-align: left;
}

.experience__inner-left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.experience__inner-right {
  align-self: flex-start;
}

.experience__title {
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  line-height: 1.2;
  margin-bottom: 2rem;
  color: var(--color-text-dark, #1A1A1A);
  font-weight: 700;
}

.experience__img {
  max-width: 17.5rem;
  height: auto;
  margin: 0 auto;
}

.experience__item {
  padding-bottom: 2rem;
  margin-bottom: 2rem;
  border-bottom: 1px solid var(--color-accent, #F7A500);
  transition: transform 0.3s ease;
}

.experience__item:hover {
  transform: translateX(0.5rem);
}

.experience__item:last-child {
  border-bottom: none;
  margin-bottom: 0;
  padding-bottom: 0;
}

.experience__subtitle {
  color: var(--color-purple);
  font-weight: 700;
  font-size: clamp(1.25rem, 2vw, 1.5rem);
  line-height: 1.3;
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.experience__icon {
  font-size: 1.5rem;
  transition: transform 0.3s ease;
}

.experience__item:hover .experience__icon {
  transform: scale(1.1);
}

.experience__text {
  font-size: clamp(1rem, 1.5vw, 1.125rem);
  line-height: 1.5;
  color: var(--color-text, #4A4A4A);
  margin-bottom: 0.5rem;
}

.experience__note {
  font-size: 0.875rem;
  color: var(--color-text-light, #666666);
  font-style: italic;
  margin-top: 0.5rem;
  padding-left: 1rem;
  border-left: 2px solid var(--color-accent, #F7A500);
}

@media (max-width: 1024px) {
  .container {
    gap: 2rem;
  }
}

@media (max-width: 768px) {
  .experience {
    padding: 3rem 0;
  }

  .container {
    flex-direction: column;
    gap: 3rem;
  }

  .experience__inner {
    width: 100%;
  }

  .experience__inner-left {
    align-items: center;
    text-align: center;
  }

  .experience__inner-right {
    margin-left: 0;
  }

  .experience__title {
    text-align: center;
  }

  .experience__item:hover {
    transform: translateX(0);
  }
}

@media (max-width: 480px) {
  .experience {
    padding: 2rem 0;
  }

  .container {
    gap: 2rem;
  }

  .experience__img {
    max-width: 15rem;
  }
}

@media (prefers-reduced-motion: reduce) {

  .experience__img,
  .experience__item,
  .experience__icon {
    transition: none;
  }

  .experience__item:hover {
    transform: none;
  }
}
</style>