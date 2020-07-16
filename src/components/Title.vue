<template>
  <div class="canvas">
    <img :src="title" class="interactive"/>
    <img :src="start" class="interactive pointer" @click="startGame" @mouseover="pressButton" @mouseleave="releaseButton" />
  </div>
</template>
<script>
import title from '../assets/images/title.gif'
import start from '../assets/images/start.png'
import starthit from '../assets/images/starthit.png'

export default {
  name: 'Title',
  data: function() {
    return {
      title: title,
      start: start,
    }
  },
  methods: {
    pressButton: function() {
      this.start = starthit
    },
    releaseButton: function() {
      this.start = start
    },
    startGame: function() {
        let self = this;
        setTimeout(function(){
            self.$emit('startGame')

        },200)
    },
  },
}
</script>
<style scoped>
img {
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 0;
}

.title {
  cursor: pointer;
}

.canvas {
  width: 80vw;
  position: relative;
  margin: auto;
  background: pink;
  top: 2vw;
}
</style>
