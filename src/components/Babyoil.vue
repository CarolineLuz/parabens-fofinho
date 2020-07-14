<template>
  <div>
    <img class="interactive" :src="image" />
    <div class="babyoil tag" @mouseenter="jump" @mouseleave="stand" @click="clicked"></div>
  </div>
</template>
<script>
import jumpy from '../assets/images/babyoiljumping.gif'
import oil from '../assets/images/babyoil.png'

export default {
  name: 'Babyoil',
  data: function() {
    return {
      image: oil,
    }
  },
  methods: {
    clicked: function() {
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
</style>
