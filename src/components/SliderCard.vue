<script setup>
defineProps({
  label: String,
  text: String,
  img: String,
  shield: String,
  href: String,
  slideNum: {
    type: Number,
    default: 1
  }
})
</script>

<template>
  <a :href="href" class="slider-card">
    <div class="slider-card__bg">
      <img src="/images/slide_bg.svg" alt="" />
    </div>
    <div class="slider-card__img">
      <img :src="`/images/sl_${slideNum}.png`" :alt="label" />
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
  width: 443px;
  position: relative;
  overflow: hidden;
  text-decoration: none;

  &__bg {
    position: absolute;
    left: 0;
    bottom: 0;
    width: 283px;
    height: 193px;
    display: flex;
    align-items: flex-end;
    z-index: 1;

    img {
      width: 100%;
      height: auto;
      max-height: 193px;
      object-fit: contain;
      object-position: left bottom;
    }
  }

  &__img {
    position: absolute;
    right: 0;
    bottom: 0;
    width: 202px;
    height: 209px;
    display: flex;
    align-items: flex-end;
    justify-content: flex-end;
    z-index: 1;

    img {
      width: auto;
      height: 209px;
      max-width: 100%;
      object-fit: contain;
      object-position: right bottom;
    }
  }

  &__shield {
    position: absolute;
    top: 10px;
    right: 10px;
    width: 40px;
    height: 40px;
    z-index: 2;

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
    z-index: 2;
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
