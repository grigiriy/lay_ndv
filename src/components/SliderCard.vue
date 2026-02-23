<script setup>
import { ref } from 'vue'

defineProps({
  label: String,
  text: String,
  img: String,
  shield: String,
  href: String,
  slideNum: {
    type: Number,
    default: 1
  },
  isMobile: {
    type: Boolean,
    default: false
  }
})

const isHovered = ref(false)
</script>

<template>
  <div class="slider-card" :class="{ 'slider-card--mobile': isMobile }" @mouseenter="isHovered = true" @mouseleave="isHovered = false">
    <div class="slider-card__bg">
      <img class="slider-card__bg-default" :src="isMobile ? '/images/slide_bg_mb.svg' : '/images/slide_bg.svg'" alt="" />
      <img v-if="!isMobile" class="slider-card__bg-hover" :class="{ active: isHovered }" src="/images/slide_bg_hover.svg" alt="" />
      <div class="slider-card__content">
        <span class="slider-card__label">{{ label }}</span>
        <p class="slider-card__text">{{ text }}</p>
        <a :href="href" class="slider-card__arrow" @click.stop>
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M2 9.85714H18.2857M18.2857 9.85714L12.022 6M18.2857 9.85714L12.022 13.7143" stroke="#1C1D21" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </a>
      </div>
    </div>
    <div class="slider-card__img">
      <img :src="`/images/sl_${slideNum}${isMobile ? '_m' : ''}.png`" :alt="label" />
    </div>
    <div class="slider-card__shield" v-if="shield">
      <img :src="shield" alt="" />
    </div>
  </div>
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

    &-default, &-hover {
      position: absolute;
      width: 100%;
      height: auto;
      max-height: 193px;
      object-fit: contain;
      object-position: left bottom;
    }

    &-hover {
      opacity: 0;
      transition: opacity 0.5s ease;
    }

    &-hover.active {
      opacity: 1;
    }
  }

  &__content {
    position: relative;
    width: 221px;
    padding-left: 15px;
    padding-top: 15px;
    z-index: 2;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    height: 100%;
  }

  &__label {
    display: inline-flex;
    align-items: center;
    height: 28px;
    padding: 0 10px;
    border-radius: 8px;
    background: radial-gradient(circle at right, #476D9F 0%, #93B2DB 99%);
    font-family: 'Inter', sans-serif;
    font-size: 10px;
    font-weight: 700;
    text-transform: uppercase;
    color: #fff;
    margin-bottom: 15px;
    transition: all 0.5s ease;
  }

  &__text {
    font-family: 'TT Norms', sans-serif;
    font-size: 16px;
    font-weight: 600;
    text-transform: uppercase;
    color: #1C1D21;
    margin: 0;
  }

  &__arrow {
    position: absolute;
    bottom: 15px;
    left: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    border-radius: 8px;
    background: #fff;
    box-shadow: 0 4px 10px 0 rgba(0, 0, 0, 0.04);
    cursor: pointer;
    transition: all 0.5s ease;
  }

  &:hover &__label {
    background: #fff;
    color: #1C1D21;
  }

  &:hover &__text {
    color: #fff;
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
    right: 8px;
    bottom: 10px;
    z-index: 2;

    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }

  &__arrow {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    border-radius: 8px;
    background: #fff;
    box-shadow: 0 4px 10px 0 rgba(0, 0, 0, 0.04);
    margin-top: 10px;
    cursor: pointer;
    transition: all 0.5s ease;

    svg path {
      transition: stroke 0.5s ease;
    }

    &:hover {
      background: #272AEB;
      box-shadow: 0 6px 15px 0 rgba(0, 0, 0, 0.08);

      svg path {
        stroke: #fff !important;
      }
    }
  }

  &--mobile {
    width: 230px;
    height: 277px;
    display: flex;
    flex-direction: column;

    .slider-card__bg {
      position: relative;
      width: 100%;
      height: 159px;
      order: 1;
      overflow: visible;

      img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }

    .slider-card__img {
      position: relative;
      width: 100%;
      height: 132px;
      order: 2;
      margin-top: -14px;

      img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }

    .slider-card__content {
      width: 100%;
      padding: 12px;
      box-sizing: border-box;
    }

    .slider-card__text {
      font-size: 12px;
    }

    .slider-card__shield {
      position: absolute;
      right: 8px;
      bottom: 8px;
    }
  }
}
</style>
