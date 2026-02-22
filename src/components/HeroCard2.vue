<template>
  <div class="hero-card-2 hero__card">
    <img src="@/assets/bg/2.svg" alt="" class="hero-card-2__img hero-card-2__img--desktop" />
    <img src="@/assets/bg/2_m.svg" alt="" class="hero-card-2__img hero-card-2__img--mobile" />
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero-card-2 {
  width: 605px;
  height: 324px;
  // background: rgba(60, 179, 113, 0.6);
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
    height: 188px;
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
