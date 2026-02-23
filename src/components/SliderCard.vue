<script setup>
defineProps({
  label: String,
  text: String,
  img: String,
  shield: String,
  href: String
})
</script>

<template>
  <a :href="href" class="slider-card">
    <div class="slider-card__img">
      <img :src="img" :alt="label" v-if="img" />
    </div>
    <div class="slider-card__shield" v-if="shield">
      <img :src="shield" alt="" />
    </div>
    <div class="slider-card__content">
      <span class="slider-card__label">{{ label }}</span>
      <p class="slider-card__text">{{ text }}</p>
    </div>
  </a>
</template>

<style lang="scss" scoped>
.slider-card {
  display: block;
  height: 209px;
  position: relative;
  overflow: hidden;
  text-decoration: none;
  background: #efefef;

  &__img {
    position: absolute;
    inset: 0;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__shield {
    position: absolute;
    top: 10px;
    right: 10px;
    width: 40px;
    height: 40px;

    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }

  &__content {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 20px;
  }

  &__label {
    display: block;
    font-family: 'Inter', sans-serif;
    font-size: 18px;
    font-weight: 600;
    color: #1C1D21;
    margin-bottom: 8px;
  }

  &__text {
    font-family: 'TT Norms', sans-serif;
    font-size: 14px;
    color: rgba(28, 29, 33, 0.8);
    margin: 0;
  }
}
</style>
