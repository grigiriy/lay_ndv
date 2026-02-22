<template>
  <div class="hero-card-4 hero__card">
    <img src="@/assets/bg/4.svg" alt="" class="hero-card-4__img hero-card-4__img--desktop" />
    <img src="@/assets/bg/4_m.svg" alt="" class="hero-card-4__img hero-card-4__img--mobile" />
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-4 {
  width: 881px;
  height: 324px;
  // background: rgba(255, 215, 0, 0.6);
  border-radius: 12px;
  margin-right: -102px;

  &__img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 12px;

    &--mobile {
      display: none;
    }
  }

  @media (max-width: 1369px) {
    width: 328px;
    height: 225px;
    margin-right: 0;
    margin-bottom: -25px;

    &__img {
      &--desktop {
        display: none;
      }
      &--mobile {
        display: block;
      }
    }
  }
}
</style>
