<script setup>
import ArticleCard from './ArticleCard.vue';
import Button from '@/components/buttons/Button.vue';

const articles = [
  {
    date: "May 3, 2021",
    title: "What is compounding?",
    description: "Compounding is the art and science of preparing personalized medications.",
    link: "#",
    image: "./articles-1.jpg"
  },
  {
    date: "June 15, 2021",
    title: "Anxiety in Pets",
    description: "An interview with a top behavioral specialist in NYC.",
    link: "#",
    image: "./articles-2.jpg"
  },
]
</script>

<template>
  <section class="articles">
    <div class="articles__inner">
      <h2 class="articles__title">In the Wild</h2>
      <p class="articles__subtitle">In The Wild is a collection of pieces to help close the communication gap, while growing the love (and understanding) between you and your best pal.</p>

      <div class="articles__items">
        <ArticleCard v-for="(item, index) in articles" :key="index" :article="item" />
      </div>

      <Button text="View More" />
    </div>
  </section>
</template>

<style scoped>
.articles {
	background-color: #FAF9F6;
	padding: 58px 0;
  position: relative;
text-align: center;
}

.articles__title {
  margin-bottom: 24px;
}

.articles__subtitle {
  max-width: 576px;
  margin: 0 auto;
}
.articles__inner {
  padding: 0 60px;
}

.articles__items {
  display: flex;
  justify-content: center;
  gap: 40px;
  margin: 84px 0 49px;
}
</style>