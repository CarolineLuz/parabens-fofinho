<template>
  <div>
    <img :src="image" />
    <div class="tag bikini" @mouseenter="flatter" @mouseleave="unflatter" @click="clicked"></div>
  </div>
</template>
<script>
import bikini from '../assets/images/bikini.png'
import windbikini from '../assets/images/windbikini.png'

export default {
  name: 'Bikini',
  data: function() {
    return {
      image: bikini,
      windbikini: windbikini,
      bikini: bikini,
    }
  },
  methods: {
    clicked: function() {
      this.$emit('clicked')
    },
    flatter: function() {
      this.image = this.windbikini
    },
    unflatter: function() {
      this.image = this.bikini
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
.bikini {
  width: 4vw;
  top: 19vw;
  left: 26vw;
  height: 6vw;
}
</style>
