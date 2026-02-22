<template>
  <div class="hero-card-3 hero__card hero__card-mob--padded">
    <img src="@/assets/bg/3.png" alt="" class="hero-card-3__img hero-card-3__img--desktop" />
    <img src="@/assets/bg/3_m.png" alt="" class="hero-card-3__img hero-card-3__img--mobile" />
    <div class="hero-card-3__content">
      <p class="hero-card-3__title">6000</p>
      <p class="hero-card-3__text">Довольных семей<br>в сданных объектах</p>
    </div>
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-3 {
  width: 463px;
  height: 324px;
  // background: rgba(30, 144, 255, 0.6);
  margin-right: 0;

  &__content {
    padding: 20px;
    padding-bottom: 32px;
    padding-left: 81px;

    @media (max-width: 1369px) {
      padding-left: 20px;
      padding-right: 20px;
    }
  }

  &__title {
    font-family: 'Inter', sans-serif;
    font-size: 42px;
    font-weight: 500;
    color: #fff;
    text-transform: uppercase;
    margin-bottom: 2px;
    margin-top: 0;
  }

  &__text {
    font-family: 'TT Norms', sans-serif;
    font-size: 18px;
    color: #fff;
    margin-bottom: 0;
    margin-top: 0;
    line-height: 1.2;
    letter-spacing: -.3px;
  }

  @media (max-width: 1369px) {
    width: 328px;
    height: 195px;
    margin-right: 0;
    margin-top: 8px;
    margin-bottom: 8px;
    &__content {
      padding-bottom: 20px;
    }
    &__title {
      font-size: 32px;
    }

    &__text {
      font-size: 16px;
    }
  }
}
</style>
