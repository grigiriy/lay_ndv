<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
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

const updateWidth = () => {
  isDesktop.value = window.innerWidth > 1369
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
  if (currentIndex.value < items.length - 3) {
    currentIndex.value++
  }
}
</script>

<template>
  <section class="slider">
    <div class="container">
      <div class="slider__viewport">
        <div class="slider__track" :style="{ transform: `translateX(-${currentIndex * 463}px)` }">
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
            />
          </div>
        </div>
      </div>
      <div class="slider__arrows">
        <button class="slider__arrow slider__arrow--prev" @click="prev" aria-label="Previous">
          ←
        </button>
        <button class="slider__arrow slider__arrow--next" @click="next" aria-label="Next">
          →
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
    gap: 10px;
    width: 60px;
  }

  &__arrow {
    width: 60px;
    height: 40px;
    background: #1C1D21;
    color: #fff;
    border: none;
    cursor: pointer;
    font-size: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background 0.3s ease;

    &:hover {
      background: #333;
    }
  }
}

@media (max-width: 1370px) {
  .slider {
    .container {
      max-width: 100%;
    }

    &__item {
      flex: 0 0 100%;
      padding: 0 20px;
    }

    &__arrows {
      position: relative;
      right: auto;
      top: auto;
      transform: none;
      flex-direction: row;
      justify-content: center;
      margin-top: 20px;
      width: auto;
    }
  }
}
</style>
