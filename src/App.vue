<template>
  <div id="app">
    <Screen/>
  </div>
</template>

<script>
import Screen from './components/Screen.vue'

export default {
  name: 'App',
  components: {
    Screen
  }
}
</script>

<style>
@font-face {
  font-family: "pixelart";
  src: url("./assets/fonts/pixelart.ttf") format('truetype')
}
#app {
  font-family: "pixelart";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100vw;
  background: black;
}
.p-relative {
  position: relative;
}
.interactive {
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 0;
}
.tag {
  cursor: pointer;
  display: block;
  /*background: red;*/
  opacity: 0.4;
  z-index: 1000;
  position: absolute;
}
</style>
