<template>
  <div class="canvas">
    <img :src="credits" class="interactive"/>
    <img :src="refresh" class="interactive"/>
  </div>
</template>
<script>
import credits from '../assets/images/credits.gif'
import refresh from '../assets/images/refreshtorestart.png'

export default {
  name: 'Credits',
  data: function() {
    return {
      credits: credits,
      refresh: refresh
    }
  }
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
.canvas {
  width: 80vw;
  position: relative;
  margin: auto;
  background: pink;
  top: 2vw;
}
</style>
