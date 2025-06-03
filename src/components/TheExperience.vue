<script setup>
</script>

<template>
  <section class="experience">
    <div class="container">
      <div class="experience__inner experience__inner-left">
        <h2 class="experience__title">We couldn’t find a pharmacy experience worthy of our best buds— so we created one.
        </h2>
        <img src="@/assets/experience-img.png" alt="Experience" class="experience__img" width="100%" height="100%">
      </div>
      <div class="experience__inner experience__inner-right">
        <div class="experience__item">
          <h3 class="experience__subtitle">Patients first, always</h3>
          <p class="experience__text">We know how stressful it can be when your pet needs meds. That’s why we offer free
            next-day delivery and even do same-day in NYC and LA. We got you.</p>
        </div>
        <div class="experience__item">
          <h3 class="experience__subtitle">Tailored care</h3>
          <p class="experience__text">We’ll work with you and your veterinarian to find the very best solution for your
            pet. With our custom compounded options, we can change the dosage, flavor and form. We even have a flavor
            guarantee with over 40 options!</p>
          <p>P.S. Everyone seems to love the chicken-flavored chew treats!</p>
        </div>
        <div class="experience__item">
          <h3 class="experience__subtitle">Support, 7 days a week</h3>
          <p class="experience__text">You’re not alone. Text, call, or email us 7 days a week—we’ll answer and do our
            best
            to sprinkle in a bit of sunshine. ☀️</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience {
  padding: 100px 20px;
}

.experience__inner {
  width: 50%;
  text-align: left;
}

.experience__inner-left {
  margin-right: 70px;
  align-items: center;
  display: flex;
  flex-direction: column;
}

.experience__inner-right {
  margin-left: 70px;
  align-self: flex-start;
}

.experience__title {
  font-size: 44px;
  line-height: 53px;
  margin-bottom: 27px;
  text-align: left;
}

.experience__img {
  max-width: 280px;
  margin: 0 auto;
}

.experience__item:not(:last-child) {
  padding-bottom: 32px;
  margin-bottom: 32px;
  border-bottom: 1px solid #F7A500;
}

.experience__subtitle {
  color: var(--color-purple);
  font-weight: 700;
  font-size: 24px;
  line-height: 31.68px;
  margin-bottom: 16px;
}

.experience__text {
  line-height: 22.72px;
}
</style>