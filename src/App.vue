<template>
  <div id="app">
    <Screen @theEnd="endGame" v-if="showScreen" />
    <Title @startGame="startGame" v-show="showTitle" />
    <Credits v-show="showCredits" />
  </div>
</template>

<script>
import Screen from './components/Screen.vue'
import Title from './components/Title.vue'
import Credits from './components/Credits.vue'

export default {
  name: 'App',
  components: {
    Screen,
    Credits,
    Title,
  },
  data: function() {
    return {
      showTitle: true,
      showScreen: false,
      showCredits: false,
    }
  },
  methods: {
    endGame: function() {
      this.showCredits = true
      this.showScreen = false
    },
    startGame: function() {
      this.showScreen = true
      this.showTitle = false
    },
  },
}
</script>

<style>
@font-face {
  font-family: 'pixelart';
  src: url('./assets/fonts/pixelart.ttf') format('truetype');
}
#app {
  font-family: 'Courier';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 13px;
  font-weight: bold;
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100vw;
  background: black;
}
.p-relative {
  position: relative;
}
.pointer {
  cursor: pointer
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
  z-index: 1000;
  position: absolute;
}
</style>
