<template>
  <div>
    <img class="interactive" :src="image" />
    <div class="whisky tag" v-if="wWhiskyClickable" @click="water"></div>
  </div>
</template>
<script>
import pouring from '../assets/images/waterplant.gif'
import whisky from '../assets/images/whisky.png'

export default {
  name: 'Whisky',
  data: function() {
    return {
      image: whisky,
    }
  },
  props: {
    wWhiskyClickable: Boolean
  },
  methods: {
    water: function() {
      let self = this
      self.$emit('savePlant')
      setTimeout(function() {
        self.image = pouring
      }, 2000)

      setTimeout(function() {
        self.image = whisky
      }, 500)
    },
  },
}
</script>
<style scoped>
.whisky {
  width: 3vw;
  height: 5vw;
  top: 28vw;
  left: 7vw;
}
</style>
