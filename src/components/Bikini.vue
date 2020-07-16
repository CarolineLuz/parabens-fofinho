<template>
  <div>
    <img :src="image" />
    <div class="tag bikini" @mouseenter="flatter" @mouseleave="unflatter" @click="clicked"></div>
    <img :src="vabali" class="vabali" v-if="showVoucher" @click="hideVoucher" />
  </div>
</template>
<script>
import bikini from '../assets/images/bikini.png'
import windbikini from '../assets/images/windbikini.png'
import vabali from '../assets/images/vabali.gif'

export default {
  name: 'Bikini',
  data: function() {
    return {
      image: bikini,
      windbikini: windbikini,
      bikini: bikini,
      vabali: null,
      showVoucher: false,
    }
  },
  methods: {
    clicked: function() {
      this.flatter()
      this.$emit('clicked')
      let self = this
      setTimeout(function() {
        self.showVoucher = true
        self.vabali = vabali
      }, 2000)
    },
    hideVoucher: function() {
      this.showVoucher = false
      this.vabali = null
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
}
.bikini {
  width: 4vw;
  top: 19vw;
  left: 26vw;
  height: 6vw;
}
.vabali {
  z-index: 8000;
  cursor: pointer;
}
</style>
