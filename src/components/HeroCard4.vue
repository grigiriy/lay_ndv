<template>
  <div class="hero-card-4 hero__card">
    <img src="@/assets/bg/4.svg" alt="" class="hero-card-4__img hero-card-4__img--desktop" />
    <img src="@/assets/bg/4_m.svg" alt="" class="hero-card-4__img hero-card-4__img--mobile" />
    <div class="hero-card-4__content">
      <p class="hero-card-4__title">Современные технологии</p>
      <p class="hero-card-4__text">Применение качественных материалов и передовых строительных решений для создания энергоэффективного и экологически чистого жилья.</p>
    </div>
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-4 {
  width: 881px;
  height: 324px;
  // background: rgba(255, 215, 0, 0.6);
  margin-right: -102px;

  &__content {
    padding: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
    padding-right: 180px;
    letter-spacing: -0.2px;
    line-height: 1.25;

    @media (max-width: 1369px) {
      padding-left: 20px;
      padding-right: 20px;
    }
  }

  &__title {
    font-family: 'Inter', sans-serif;
    font-size: 30px;
    font-weight: 700;
    color: #1C1D21;
    text-transform: uppercase;
    margin-bottom: 13px;
    margin-top: 0;
  }

  &__text {
    font-family: 'TT Norms', sans-serif;
    font-size: 18px;
    color: rgba(28, 29, 33, 0.8);
    margin-top: 0;
    margin-bottom: 0;
  }

  @media (max-width: 1369px) {
    width: 328px;
    height: 225px;
    margin-right: 0;
    margin-bottom: -25px;

    &__title {
      font-size: 22px;
    }

    &__text {
      font-size: 16px;
    }
  }
}
</style>
