<template>
  <section class="hero">
    <div class="container">
      <div class="hero__grid">
        <div class="hero__row hero__row--1">
          <HeroCard1 />
          <HeroCard2 />
          <HeroCard3 />
        </div>
        <div class="hero__row hero__row--2">
          <HeroCard4 />
          <HeroCard5 />
        </div>
      </div>

      <div class="hero__mobile">
        <HeroCard1 />
        <HeroCard2 />
        <HeroCard3 />
        <HeroCard4 />
        <HeroCard5 />
      </div>
    </div>
  </section>
</template>

<script setup>
import HeroCard1 from './HeroCard1.vue'
import HeroCard2 from './HeroCard2.vue'
import HeroCard3 from './HeroCard3.vue'
import HeroCard4 from './HeroCard4.vue'
import HeroCard5 from './HeroCard5.vue'
</script>

<style lang="scss" scoped>
.hero {
  padding: 40px 0;

  &__grid {
    display: flex;
    flex-direction: column;
  }

  &__row {
    display: flex;

    &--1 {
      margin-bottom: 13px;
    }
  }

  &__mobile {
    display: none;
  }

  @media (max-width: 1369px) {
    &__grid {
      display: none;
    }

    &__mobile {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 328px;
      margin: 0 auto;
    }
  }
}
</style>
