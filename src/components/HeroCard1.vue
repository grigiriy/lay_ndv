<template>
  <div class="hero-card-1 hero__card">
    <img src="@/assets/bg/1.svg" alt="" class="hero-card-1__img hero-card-1__img--desktop" />
    <img src="@/assets/bg/1_m.svg" alt="" class="hero-card-1__img hero-card-1__img--mobile" />
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-1 {
  width: 513px;
  height: 324px;
  // background: rgba(255, 99, 71, 0.6);
  border-radius: 12px;
  margin-right: -105.5px;

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
    height: 202px;
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
