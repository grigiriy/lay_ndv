<template>
  <section class="hero">
    <div class="container">
      <div class="hero__grid">
        <div class="hero__row hero__row--1">
          <div class="hero__card" style="--w: 513px; --c: rgba(255, 99, 71, 0.6)"></div>
          <div class="hero__card" style="--w: 605px; --c: rgba(60, 179, 113, 0.6)"></div>
          <div class="hero__card" style="--w: 463px; --c: rgba(30, 144, 255, 0.6)"></div>
        </div>
        <div class="hero__row hero__row--2">
          <div class="hero__card hero__card--wide" style="--w: 881px; --c: rgba(255, 215, 0, 0.6)"></div>
          <div class="hero__card" style="--w: 591px; --c: rgba(238, 130, 238, 0.6)"></div>
        </div>
      </div>

      <!-- Mobile version -->
      <div class="hero__mobile">
        <div class="hero__card-mob" style="--h: 202px; --c: rgba(255, 99, 71, 0.6)"></div>
        <div class="hero__card-mob" style="--h: 188px; --c: rgba(60, 179, 113, 0.6)"></div>
        <div class="hero__card-mob hero__card-mob--padded" style="--h: 195px; --c: rgba(30, 144, 255, 0.6)"></div>
        <div class="hero__card-mob" style="--h: 225px; --c: rgba(255, 215, 0, 0.6)"></div>
        <div class="hero__card-mob" style="--h: 215px; --c: rgba(238, 130, 238, 0.6)"></div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.hero {
  padding: 40px 0;

  &__grid {
    display: flex;
    flex-direction: column;
  }

  &__row {
    display: flex;

    &--1 {
      margin-bottom: 13px;
    }
  }

  &__card {
    width: var(--w);
    height: 300px;
    background: var(--c);
    border-radius: 12px;
    margin-right: -105.5px;

    &:last-child {
      margin-right: 0;
    }

    &--wide {
      margin-right: -102px;
    }
  }

  &__mobile {
    display: none;
  }

  @media (max-width: 1369px) {
    &__grid {
      display: none;
    }

    &__mobile {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 328px;
      margin: 0 auto;
    }

    &__card-mob {
      width: 328px;
      height: var(--h);
      background: var(--c);
      border-radius: 12px;

      &:nth-child(1),
      &:nth-child(4) {
        margin-bottom: -25px;
      }

      &--padded {
        margin-top: 8px;
        margin-bottom: 8px;
      }
    }
  }
}
</style>