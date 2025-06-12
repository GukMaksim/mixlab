<script setup>
import ArticleCard from './ArticleCard.vue';
import Button from '@/components/buttons/Button.vue';

const articles = [
  {
    id: 1,
    date: "May 3, 2021",
    title: "What is compounding?",
    description: "Compounding is the art and science of preparing personalized medications.",
    link: "#",
    image: "./articles-1.jpg",
    category: "Pet Care"
  },
  {
    id: 2,
    date: "June 15, 2021",
    title: "Anxiety in Pets",
    description: "An interview with a top behavioral specialist in NYC.",
    link: "#",
    image: "./articles-2.jpg",
    category: "Behavior"
  }
];
</script>

<template>
  <section class="articles" aria-labelledby="articles-title">
    <img class="articles__img-left" src="@/assets/articles-img-left.png" alt="Decorative element" width="200"
      height="200" loading="lazy">
    <img class="articles__img-right" src="@/assets/articles-img-right.png" alt="Decorative element" width="200"
      height="200" loading="lazy">

    <div class="articles__inner">
      <h2 id="articles-title" class="articles__title">
        In the Wild
      </h2>

      <p class="articles__subtitle">
        In The Wild is a collection of pieces to help close the communication gap,
        while growing the love (and understanding) between you and your best pal.
      </p>

      <div class="articles__items" role="list" aria-label="Articles list">
        <ArticleCard v-for="article in articles" :key="article.id" :article="article" role="listitem" />
      </div>

      <Button text="View More" class="articles__button" aria-label="View more articles" variant="primary"
        size="large" />
    </div>
  </section>
</template>

<style scoped>
.articles {
  background-color: var(--color-background-light, #FAF9F6);
  padding: 4rem 0;
  position: relative;
  text-align: center;
  overflow: hidden;
}

.articles__img-left,
.articles__img-right {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: auto;
  height: auto;
  max-width: 12.5rem;
  opacity: 0.8;
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.articles__img-left {
  right: 0;
}

.articles__img-right {
  left: 0;
}

.articles__img-left:hover,
.articles__img-right:hover {
  opacity: 1;
  transform: translateY(-50%) scale(1.05);
}

.articles__inner {
  position: relative;
  z-index: 1;
  padding: 0 1rem;
  max-width: 90rem;
  margin: 0 auto;
}

.articles__title {
  font-size: clamp(2rem, 4vw, 3rem);
  line-height: 1.2;
  margin-bottom: 1.5rem;
  color: var(--color-text-dark, #1A1A1A);
  font-weight: 700;
}

.articles__subtitle {
  max-width: 36rem;
  margin: 0 auto;
  font-size: clamp(1rem, 1.5vw, 1.125rem);
  line-height: 1.5;
  color: var(--color-text, #4A4A4A);
}

.articles__items {
  display: flex;
  justify-content: center;
  gap: 2.5rem;
  margin: 5rem 0 3rem;
  flex-wrap: wrap;
}

.articles__button {
  margin-top: 2rem;
}

@media (max-width: 1024px) {
  .articles__items {
    gap: 2rem;
  }

  .articles__img-left,
  .articles__img-right {
    max-width: 9.375rem;
  }
}

@media (max-width: 768px) {
  .articles {
    padding: 3rem 0;
  }

  .articles__img-left,
  .articles__img-right {
    display: none;
  }

  .articles__items {
    margin: 3rem 0 2rem;
  }
}

@media (max-width: 480px) {
  .articles {
    padding: 2rem 0;
  }

  .articles__inner {
    padding: 0;
  }

  .articles__items {
    gap: 1.5rem;
    margin: 2rem 0 1.5rem;
  }
}

@media (prefers-reduced-motion: reduce) {

  .articles__img-left,
  .articles__img-right {
    transition: none;
  }

  .articles__img-left:hover,
  .articles__img-right:hover {
    transform: translateY(-50%);
  }
}
</style>