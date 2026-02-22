<template>
  <div class="hero-card-1 hero__card">
    <img src="@/assets/bg/1.svg" alt="" class="hero-card-1__img hero-card-1__img--desktop" />
    <img src="@/assets/bg/1_m.svg" alt="" class="hero-card-1__img hero-card-1__img--mobile" />
    <div class="hero-card-1__content">
      <p class="hero-card-1__title">15<span>+</span></p>
      <p class="hero-card-1__text">лет на рынке<br>недвижимости</p>
    </div>
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-1 {
  width: 513px;
  height: 324px;
  // background: rgba(255, 99, 71, 0.6);
  margin-right: -105.5px;

  &__content {
    padding: 20px;
    padding-bottom: 24px;
    padding-left: 40px;

    @media (max-width: 1369px) {
      padding-left: 20px;
      padding-right: 20px;
    }
  }

  &__title {
    font-family: 'Inter', sans-serif;
    font-size: 160px;
    font-weight: 500;
    color: #1C1D21;
    text-transform: uppercase;
    margin-bottom: -12px;
    margin-top: 0;
    line-height: 1.25;
    letter-spacing: -0.2px;

    span {
      bottom: 10px;
      position: relative;
    }
  }

  &__text {
    font-family: 'TT Norms', sans-serif;
    font-size: 26px;
    line-height: 1.3;
    font-weight: 600;
    color: #1C1D21;
    text-transform: uppercase;
    margin-bottom: 0;
    margin-top: 0;
  }

  @media (max-width: 1369px) {
    width: 328px;
    height: 202px;
    margin-right: 0;
    margin-bottom: -25px;
    &__title {
      font-size: 100px;
    }

    &__text {
      font-size: 18px;
      margin-bottom: 8px;
    }
  }
}
</style>
