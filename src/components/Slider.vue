<script setup>
import { ref, onMounted, onUnmounted, computed } from 'vue'
import SliderCard from './SliderCard.vue'

const currentIndex = ref(0)
const items = [
  { id: 1, label: 'до 12 июня 2025', text: 'Сертификат на мебель в подарок', slideNum: 1, shield: '/images/shield_1.svg', href:'#' },
  { id: 2, label: 'до 13 июня 2025', text: 'Выгодное предложение на старте продаж', slideNum: 2, shield: '/images/shield_2.svg', href:'#' },
  { id: 3, label: 'до 14 июня 2025', text: 'Отделка в подарок при покупке', slideNum: 3, shield: '/images/shield_3.svg', href:'#' },
  { id: 4, label: 'до 15 июня 2025', text: 'Сертификат на мебель в подарок', slideNum: 1, shield: '/images/shield_1.svg', href:'#' },
  { id: 5, label: 'до 16 июня 2025', text: 'Выгодное предложение на старте продаж', slideNum: 2, shield: '/images/shield_2.svg', href:'#' },
  { id: 6, label: 'до 17 июня 2025', text: 'Отделка в подарок при покупке', slideNum: 3, shield: '/images/shield_3.svg', href:'#' },
]

const isDesktop = ref(window.innerWidth > 1369)
const isMobile = ref(window.innerWidth < 1369)

const updateWidth = () => {
  isDesktop.value = window.innerWidth > 1369
  isMobile.value = window.innerWidth < 1369
}

onMounted(() => {
  window.addEventListener('resize', updateWidth)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateWidth)
})

const prev = () => {
  if (currentIndex.value > 0) {
    currentIndex.value--
  }
}

const next = () => {
  if (isMobile.value) {
    if (currentIndex.value < items.length - 1) {
      currentIndex.value++
    }
  } else {
    if (currentIndex.value < items.length - 3) {
      currentIndex.value++
    }
  }
}

const canPrev = () => currentIndex.value > 0
const canNext = computed(() => {
  if (isMobile.value) {
    return currentIndex.value < items.length - 1
  }
  return currentIndex.value < items.length - 3
})

const slideWidth = computed(() => isMobile.value ? 230 : 443)
const slideGap = computed(() => isMobile.value ? 15 : 20)
const step = computed(() => slideWidth.value + slideGap.value)

let touchStartX = 0
let touchEndX = 0

const onTouchStart = (e) => {
  touchStartX = e.changedTouches[0].screenX
}

const onTouchEnd = (e) => {
  touchEndX = e.changedTouches[0].screenX
  handleSwipe()
}

const handleSwipe = () => {
  const diff = touchStartX - touchEndX
  if (Math.abs(diff) > 50) {
    if (diff > 0) {
      next()
    } else {
      prev()
    }
  }
}
</script>

<template>
  <section class="slider">
    <div class="container">
      <div class="slider__viewport">
        <div 
          class="slider__track" 
          :style="{ transform: `translateX(-${currentIndex * step}px)` }"
          @touchstart="onTouchStart"
          @touchend="onTouchEnd"
        >
          <div 
            class="slider__item"
            v-for="(item, index) in items" 
            :key="item.id"
          >
            <SliderCard 
              :label="item.label"
              :text="item.text"
              :slideNum="item.slideNum"
              :href="item.href"
              :shield="item.shield"
              :isMobile="isMobile"
            />
          </div>
        </div>
      </div>
      <div class="slider__arrows" v-if="!isMobile">
        <button 
          class="slider__arrow" 
          :class="{ 'slider__arrow--disabled': !canPrev() }"
          @click="prev" 
          :disabled="!canPrev()" 
          aria-label="Previous"
        >
          <img src="/images/arrow.svg" alt="" class="slider__arrow--next-icon" />
        </button>
        <button 
          class="slider__arrow" 
          :class="{ 'slider__arrow--disabled': !canNext }"
          @click="next" 
          :disabled="!canNext" 
          aria-label="Next"
        >
          <img src="/images/arrow.svg" alt="" />
        </button>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.slider {
  position: relative;
  padding: 40px 0;

  .container {
    // background: yellow;
    max-width: 1369px;
    margin: 0 auto;
    padding: 0;
    position: relative;
  }

  &__track {
    display: flex;
    gap: 20px;
    transition: transform 0.4s ease;
    box-sizing: border-box;
  }

  &__viewport {
    overflow: hidden;
  }

  &__item {
    flex: 0 0 443px;
  }

  &__arrows {
    position: absolute;
    right: -20px;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    flex-direction: column;
    gap: 0;
    width: 60px;
    height: 110px;
    background: rgba(#1C1D21, 0.4);
    border-radius: 16px;
    padding: 5px;
    box-sizing: border-box;
    backdrop-filter: blur(10px);
  }

  &__arrow {
    width: 50px;
    height: 50px;
    background: transparent;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
    border-radius: 12px;

    img {
      width: 20px;
      height: 20px;
    }

    &--next-icon {
      transform: rotate(180deg);
    }

    &--disabled {
      opacity: 0.4;
      cursor: not-allowed;
    }

    &:last-child {
      border-top: 1px solid rgba(255, 255, 255, 0.4);
    }
  }
}

@media (max-width: 1369px) {
  .slider {
    .container {
      max-width: 360px;
      padding: 0;
      margin: 0 auto;
      box-sizing: border-box;
      overflow: hidden;
    }

    &__track {
      gap: 15px;
    }

    &__viewport {
      overflow: hidden;
      padding: 0 15px;
      box-sizing: border-box;
    }

    &__item {
      flex: 0 0 230px;
      height: 277px;
    }

    &__arrows {
      display: none;
    }
  }
}
</style>
