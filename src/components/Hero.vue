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

    padding: 20px 0;

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

:deep(.hero-card-1),
:deep(.hero-card-2),
:deep(.hero-card-3),
:deep(.hero-card-4),
:deep(.hero-card-5) {
  position: relative;
  overflow: hidden;
  border-radius: 12px;
  box-sizing: border-box;
}

:deep(.hero-card-1__img),
:deep(.hero-card-2__img),
:deep(.hero-card-3__img),
:deep(.hero-card-4__img),
:deep(.hero-card-5__img) {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

:deep(.hero-card-1__img--mobile),
:deep(.hero-card-2__img--mobile),
:deep(.hero-card-3__img--mobile),
:deep(.hero-card-4__img--mobile),
:deep(.hero-card-5__img--mobile) {
  display: none;
}

@media (max-width: 1369px) {
  :deep(.hero-card-1__img--desktop),
  :deep(.hero-card-2__img--desktop),
  :deep(.hero-card-3__img--desktop),
  :deep(.hero-card-4__img--desktop),
  :deep(.hero-card-5__img--desktop) {
    display: none;
  }

  :deep(.hero-card-1__img--mobile),
  :deep(.hero-card-2__img--mobile),
  :deep(.hero-card-3__img--mobile),
  :deep(.hero-card-4__img--mobile),
  :deep(.hero-card-5__img--mobile) {
    display: block;
  }
}

:deep(.hero-card-1__content),
:deep(.hero-card-2__content),
:deep(.hero-card-3__content),
:deep(.hero-card-4__content),
:deep(.hero-card-5__content) {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  height: 100%;
  box-sizing: border-box;
}
</style>
