<template>
  <div class="hero-card-2 hero__card">
    <img src="@/assets/bg/2.svg" alt="" class="hero-card-2__img hero-card-2__img--desktop" />
    <img src="@/assets/bg/2_m.svg" alt="" class="hero-card-2__img hero-card-2__img--mobile" />
    <div class="hero-card-2__content">
      <p class="hero-card-2__title">Надежность</p>
      <p class="hero-card-2__text">Стабильная работа без задержек, прозрачные договоры и честные отношения с каждым покупателем на протяжении всего сотрудничества.</p>
    </div>
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-2 {
  width: 605px;
  height: 324px;
  // background: rgba(60, 179, 113, 0.6);
  margin-right: -105.5px;

  &__content {
    padding: 20px;
    padding-bottom: 30px;
    padding-left: 92px;
    padding-right: 182px;

    @media (max-width: 1369px) {
      padding-left: 20px;
      padding-right: 20px;
    }
  }

  &__title {
    font-family: 'Inter', sans-serif;
    font-size: 30px;
    font-weight: 700;
    letter-spacing: -0.8px;
    color: #ffffffbe;
    text-transform: uppercase;
    margin-bottom: 12px;
    margin-top: 0;
  }

  &__text {
    font-family: 'TT Norms', sans-serif;
    font-size: 18px;
    line-height: 1.3;
    letter-spacing: -0.3px;
    color: rgba(255, 255, 255, 0.8);
    margin-top: 0;
    margin-bottom: 0;
  }

  @media (max-width: 1369px) {
    width: 328px;
    height: 188px;
    margin-right: 0;
    &__content {
      padding-bottom: 20px;
    }
    &__title {
      font-size: 22px;
    }

    &__text {
      font-size: 16px;
    }
  }
}
</style>
