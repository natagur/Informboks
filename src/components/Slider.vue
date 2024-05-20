<template>
    <div class="slider">
      <div class="container">
        <div class="slider__wrap" ref="refSliderWrap">
          <div class="slider__wrap-container" v-bind:style="'margin-left:-' + leftPosition + 'px'">
            <SliderItem
              v-for="(slider, index) in sliders" :key="index"
              v-bind:subtitle="slider.subtitle"
              v-bind:text="slider.text"
              v-bind:textButton="slider.textButton"
              v-bind:linkButton="slider.linkButton"
              v-bind:image="slider.image"
            />
          </div>
        </div>
        <div class="slider__button">
          <ul>
            <li v-for="(slider, index) in sliders" :key="index"
             v-bind:class="myActiveSlider == index ? 'active' : ''"
             @click="handleSliderChange(index)">
              <SvgIcon v-if="myActiveSlider == index" name="greenPoint"/>
              <SvgIcon v-else name="grayPoint"/>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import SliderItem from './SliderItem.vue'
  import SvgIcon from './SvgIcon.vue'

  export default {
    name: 'HeaderInfo',
    props: {
      activeSlider: Number,
    },
    components: {
      SliderItem,
      SvgIcon,
    },
    data: function(){
      return {
        sliders: [
          {
            subtitle: 'Classic Brokerage MT4 | MT5',
            text: 'Stay classic, brand and launch your own brokerage business in the most reliable trading platform in the globe. About 4 million users operates on a daily basis in Metatrader.',
            textButton: 'how it work',
            linkButton: '/',
            image: require('./../assets/img/slider1.png'),
          },
          {
            subtitle: 'Classic Brokerage MT4 | MT5',
            text: 'Stay classic, brand and launch your own brokerage business in the most reliable trading platform in the globe. About 4 million users operates on a daily basis in Metatrader.',
            textButton: 'how it work',
            linkButton: '/',
            image: require('./../assets/img/slider2.png'),
          },
          {
            subtitle: 'Classic Brokerage MT4 | MT5',
            text: 'Stay classic, brand and launch your own brokerage business in the most reliable trading platform in the globe. About 4 million users operates on a daily basis in Metatrader.',
            textButton: 'how it work',
            linkButton: '/',
            image: require('./../assets/img/slider3.png'),
          },
          {
            subtitle: 'Classic Brokerage MT4 | MT5',
            text: 'Stay classic, brand and launch your own brokerage business in the most reliable trading platform in the globe. About 4 million users operates on a daily basis in Metatrader.',
            textButton: 'how it work',
            linkButton: '/',
            image: require('./../assets/img/slider4.png'),
          },
        ],
        myActiveSlider: this.activeSlider
      }  
    },
    methods: {
      handleSliderChange(linkId) {
        this.myActiveSlider = linkId;
      }
    },
    computed: {
      leftPosition() {
        let width = 0;
        if (typeof this.$refs.refSliderWrap !== 'undefined') {
          width = this.$refs.refSliderWrap.offsetWidth;
        }
        return this.myActiveSlider * width;
      }
    },
    watch: {
      activeSlider(newValue) {
        this.myActiveSlider = newValue;
      }
    },
  }
  </script>
  
  <style scoped lang="scss">
  .slider {
    .slider__wrap {
      width: 100%;
      overflow: hidden;
      .slider__wrap-container {
        flex-wrap: nowrap;
        display: flex;
        align-items: baseline;
        width: calc(400% + 1px);
        transition-timing-function: ease-in-out;
        transition-duration: 0.3s;
      }
    }
    .slider__button {
      ul {
        list-style-type: none;
        display: flex;
        justify-content: center;
        li {
          margin-right: 11px;
          &:last-child {
          margin-right: 0px;
          }
        }
      }
    }
  }
  </style>
  