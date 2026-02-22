<template>
  <div class="hero-card-5 hero__card">
    <img src="@/assets/bg/5.svg" alt="" class="hero-card-5__img hero-card-5__img--desktop" />
    <img src="@/assets/bg/5_m.svg" alt="" class="hero-card-5__img hero-card-5__img--mobile" />
    <div class="hero-card-5__content">
      <p class="hero-card-5__title">1 <span>млн м</span><sup>2</sup></p>
      <p class="hero-card-5__text">Коттеджных поселков<br>и жилых районов</p>
    </div>
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-5 {
  width: 591px;
  height: 324px;
  // background: rgba(238, 130, 238, 0.6);
  margin-right: 0;

  &__content {
    padding: 20px;
    padding-bottom: 24px;
    padding-left: 131px;

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
    white-space: nowrap;

    span {
      font-size: 32px;
      margin-left: -40px;
      letter-spacing: -2.2px;
    }
    sup {
      font-size: 20px;
      bottom: -42px;
      position: relative;
      font-weight: 600;
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
    height: 215px;
    margin-right: 0;
    &__content {
      padding-bottom: 10px;
    }
    &__title {
      font-size: 100px;
      margin-bottom: 0;

      span {
        margin-left: -24px;
        font-size: 22px;
      }

      sup {
        font-size: 18px;
          bottom: -26px;
      }
    }

    &__text {
      font-size: 18px;
    }
  }
}
</style>
