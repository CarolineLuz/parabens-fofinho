<template>
  <div>
    <img :src="image" v-if="show" />
    <div class="tag kallax"  @click="findPresent"></div>
  </div>
</template>
<script>
import kallax from '../assets/images/presikallax.png'

export default {
  name: 'Kallax',
  data: function() {
    return {
      image: kallax,
      show: false
    }
  },
  methods: {
    findPresent: function() 
    {
      if (!this.show) {
        this.$emit("found")
      }
      this.show = true;
      
    }
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
.kallax {
  width: 5vw;
  top: 34vw;
  left: 74vw;
  height: 6vw;
}
</style>
