<template>
  <div class="slider__item">
    <div class="slider__item-left">
      <p class="slider__item-subtitle">{{ subtitle }}</p>
      <p class="slider__item-descr">{{ text }}</p>
      <a v-bind:href="linkButton" class="slider__item-link">{{ textButton }}</a>
    </div>
    <div class="slider__item-right">
      <img v-bind:src="image" alt="">
    </div>
  </div>
</template>

<script>
  export default {
    name: 'SliderItem',
    props: {
      subtitle: String,
      text: String,
      textButton: String,
      linkButton: String,
      image: String,
    }
  }
</script>

<style scoped lang="scss">
  .slider__item {
      display: flex;
      justify-content: space-between;
      position: relative;
      min-height: 45vw;
    .slider__item-left {
      width: 41%;
      text-align: left;
      position: relative;
      z-index: 1;
      .slider__item-subtitle {
        font-size: 64px;
        line-height: 70px;
        font-weight: 700;
        color: #000000;
        margin: 0;
        margin-bottom: 20px;
        @media (max-width: 520px) {
          font-size: 32px;
          line-height: 42px;
        }
      }
      .slider__item-descr {
        margin: 0;
        font-size: 20px;
        line-height: 30px;
        font-weight: 400;
        letter-spacing: 7%;
        margin-bottom: 35px; 
        color: #3F3F3F;
        width: 74%;
        @media (max-width: 1020px) {
          width: 100%;
        }
        @media (max-width: 520px) {
          font-size: 16px;
          line-height: 20px;
        }
      }
      .slider__item-link {
        font-family: "Roboto", sans-serif;
        font-size: 16px;
        line-height: 45px;
        font-weight: 700;
        color: #fff;
        text-decoration: none;
        border-radius: 10px;
        background: #547966;
        padding: 14px 42px;
        transition-timing-function: ease-in-out;
        transition-property: background;
        transition-duration: 0.3s;
        &:hover {
          background: #5EB086
        }
      }
      @media (max-width: 1020px) {
        width: 100%;
      }
    }
    .slider__item-right {
      width: 68%;
      right: 0;
      position: absolute;
      z-index: 0;
      top: 17%;
      img {
        width: 100%;
      }
      @media (max-width: 1020px) {
        position: inherit;
        width: 100%;
      }
    }
    @media (max-width: 1020px) {
      flex-direction: column;
    }
  }
</style>
  