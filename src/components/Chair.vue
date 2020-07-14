<template>
  <div>
    <img class="interactive" :src="image" />
    <div class="chair tag" @click="doTheDance"></div>
  </div>
</template>
<script>
import chair from '../assets/images/chair.png'
import chairdance from '../assets/images/chairdance.gif'

export default {
  name: 'Chair',
  data: function() {
    return {
      image: chair,
    }
  },
  methods: {
    doTheDance: function() {
      this.image = chairdance;
      this.$emit('chairdance')
      let self = this
      setTimeout(function() {
        self.image = chair
      }, 700)
    }

  },
}
</script>
<style scoped>
.chair {
  width: 5vw;
  height: 11vw;
  top: 18vw;
  left: 62vw;
}
</style>
