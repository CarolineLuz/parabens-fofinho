<template>
  <div>
    <img class="interactive" :src="image" />
    <div class="caro tag" @click="talk"></div>
    <img class="interactive" v-if="talking" :src="speechbubble" />
    <p class="talk" v-if="talking">{{ text[0] }}</p>
    <span class="close" v-if="talking" @click="stopTalking"></span>
  </div>
</template>
<script>
import caro from '../assets/images/caro.png'
import speechbubble from '../assets/images/speechbubble.png'
import talkingcaro from '../assets/images/talkingcaro.gif'
import text from '../utils/text.js';

export default {
  name: 'Caro',
  data: function() {
    return {
      image: caro,
      talking: false,
      text: text.speechbubbles,
      speechbubble: speechbubble,
    }
  },
  methods: {
    talk: function() {
      this.talking = true
      this.$emit('talking')
      this.image = talkingcaro
    },
    stopTalking: function() {
      this.text.shift()
      this.talking = false
      this.image = caro
    },
  },
}
</script>
<style scoped>
.caro {
  width: 6vw;
  height: 12vw;
  top: 22vw;
  left: 31vw;
}

.close {
  position: absolute;
  cursor: pointer;
  left: 31vw;
  top: 17.5vw;
  z-index: 2000;
  height: 1.5vw;
  width: 1.5vw;
}
.talk {
  position: absolute;
  left: 21vw;
  top: 11vw;
  height: 4vw;
  width: 11vw;
}
</style>
