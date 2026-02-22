<template>
  <div class="hero-card-3 hero__card hero__card-mob--padded">
    <img src="@/assets/bg/3.png" alt="" class="hero-card-3__img hero-card-3__img--desktop" />
    <img src="@/assets/bg/3_m.png" alt="" class="hero-card-3__img hero-card-3__img--mobile" />
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-3 {
  width: 463px;
  height: 324px;
  // background: rgba(30, 144, 255, 0.6);
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
    height: 195px;
    margin-right: 0;
    margin-bottom: 0;
    margin-top: 8px;
    margin-bottom: 8px;

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
