<template>
  <div class="hero-card-5 hero__card">
    <img src="@/assets/bg/5.svg" alt="" class="hero-card-5__img hero-card-5__img--desktop" />
    <img src="@/assets/bg/5_m.svg" alt="" class="hero-card-5__img hero-card-5__img--mobile" />
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-5 {
  width: 591px;
  height: 324px;
  // background: rgba(238, 130, 238, 0.6);
  border-radius: 12px;
  margin-right: 0;

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
    height: 215px;
    margin-right: 0;

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
