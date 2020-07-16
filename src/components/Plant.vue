<template>
  <div>
    <img class="interactive" :src="image" />
    <div class="plant tag" @click="die"></div>
  </div>
</template>
<script>
import lives from '../assets/images/plantlives.gif'
import dies from '../assets/images/plantdies.gif'
import plant from '../assets/images/plant.png'

export default {
  name: 'Plant',
  data: function() {
    return {
      image: plant,
    }
  },
  methods: {
    die: function() {
      this.image = dies;
      this.$emit('plantDied')
    },
    live: function() {
      let self = this
      setTimeout(function() {
        self.image = (self.image == dies ) ? lives: plant
      }, 2500)
    },
  },
}
</script>
<style scoped>
.plant {
  width: 6vw;
  height: 12vw;
  top: 19vw;
  left: 2vw;
}
</style>
