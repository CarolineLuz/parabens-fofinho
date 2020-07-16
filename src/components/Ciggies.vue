<template>
  <div>
    <img :src="ciggies" v-if="show && !showAnimation" />
    <div class="tag ciggies" @mouseenter="show = true" @mouseleave="reset" @click="pow"></div>
    <img :src="ciggiespow" v-if="showAnimation" class="pow" @click="showAnimation = false"/>
  </div>
</template>
<script>
import ciggies from '../assets/images/ciggies.png'
import ciggiespow from '../assets/images/ciggies.gif'

export default {
  name: 'Ciggies',
  data: function() {
    return {
      ciggies: ciggies,
      show: false,
      ciggiespow: ciggiespow,
      showAnimation: false
    }
  },
  methods: {
    pow: function() {
      this.$emit('found')
      this.showAnimation = true
      let self = this
      setTimeout(function() {
        self.showAnimation = false
      }, 1900)
    },
    reset: function() {
      if (!this.showAnimation) {
        this.show = false
        this.image = ciggies
      }
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
.ciggies {
  width: 5vw;
  top: 32vw;
  left: 30vw;
  height: 4vw;
}
.pow {
  cursor: pointer;
}
</style>
