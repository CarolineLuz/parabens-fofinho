<template>
  <div>
    <img class="interactive" :src="image" />
    <div class="lamp1 tag" @click="party"></div>
    <div class="lamp2 tag" @click="party"></div>
    <div class="lamp3 tag" @click="party"></div>
  </div>
</template>
<script>
import bling from '../assets/images/lampsbling.gif'
import lamps from '../assets/images/lamps.png'

export default {
  name: 'Lamps',
  data: function() {
    return {
      image: lamps,
    }
  },
  methods: {
    party: function() {
        this.image = (this.image == bling) ? lamps : bling
    },
  },
}
</script>
<style scoped>
.lamp1 {
  width: 3vw;
  height: 5vw;
  top: 0vw;
  left: 50vw;
}
.lamp2 {
  width: 3vw;
  height: 15vw;
  top: 0vw;
  left:54vw;
}
.lamp3 {
  width: 3vw;
  height: 10vw;
  top: 0vw;
  left: 58vw;
}
</style>
