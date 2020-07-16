<template>
  <div>
    <img class="interactive" :src="image" />
    <div class="babyoil tag" @mouseenter="jump" @mouseleave="stand" @click="clicked"></div>
    <img class="voucher" :src="voucher" v-if="showVoucher" @click="showVoucher = false"/>
  </div>
</template>
<script>
import jumpy from '../assets/images/babyoiljumping.gif'
import oil from '../assets/images/babyoil.png'
import voucher from '../assets/images/massage.png'

export default {
  name: 'Babyoil',
  data: function() {
    return {
      image: oil,
      voucher: voucher,
      showVoucher: false
    }
  },
  methods: {
    clicked: function() {
      let self = this;
      setTimeout(function() {
        self.showVoucher = true;
      }, 2000)
      this.$emit('clicked')
    },
    jump: function() {
        this.image = jumpy 
    },
    stand: function() {
        this.image = oil 
    },
  },
}
</script>
<style scoped>
.babyoil {
  width: 2vw;
  height: 3vw;
  top: 20vw;
  left: 49vw;
}
.voucher {
  cursor: pointer;
  z-index: 10000;
}
</style>
