<template>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" rel="stylesheet">
  <header>
    <HeaderInfo/>
    <HeaderMenu @idClicked="handleMenu"/>
  </header>
  <section>
    <Slider v-bind:activeSlider="activeSlider"/>
  </section>
</template>

<script>
import HeaderInfo from './components/HeaderInfo.vue'
import HeaderMenu from './components/HeaderMenu.vue'
import Slider from './components/Slider.vue'

export default {
  name: 'App',
  components: {
    HeaderInfo,
    HeaderMenu,
    Slider
  },
  data: function(){
    return {
      activeSlider: 0
    }
  },
  methods: {
    handleMenu(id) {
      this.activeSlider = id;
    }
  }
}
</script>

<style lang="scss">
body {
    margin: 0;
    box-sizing: inherit;
}  

#app {
  font-family: "Inter", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #FCFBFB;
}

.container {
  max-width: 1480px;
  padding-right: 20px;
  padding-left: 20px;
  margin: auto;
}
</style>
