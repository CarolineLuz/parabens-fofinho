<template>
  <div>
    <img class="interactive" v-if="show" :src="image" />
    <div class="asmon tag" @click="show = !show"></div>
  </div>
</template>
<script>
import asmongold from '../assets/images/asmongold.png'

export default {
  name: 'WOW',
  data: function() {
    return {
      image: asmongold,
      show: false
    }
  }
}
</script>
<style scoped>
.asmon {
  width: 5vw;
  height: 5vw;
  top: 18vw;
  left: 54vw;
}
</style>
