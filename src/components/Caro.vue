<template>
  <div>
    <div v-if="!allPresentsFound">
      <img class="interactive" :src="image" />
      <div class="caro tag" @click="talk"></div>
      <img class="interactive" v-if="talking" :src="speechbubble" />
      <p class="talk" v-if="talking">{{ text[currentIndex] }}</p>
      <span class="close" v-if="talking" @click="stopTalking"></span>
    </div>
    <div v-else>
      <img class="interactive" :src="carowithletter"  />
      <div class="letter tag" @click="readLetter"></div>
    </div>
  </div>
</template>
<script>
import caro from '../assets/images/caro.png'
import speechbubble from '../assets/images/speechbubble.png'
import carowithletter from '../assets/images/carowithletter.png'
import caroblushing from '../assets/images/caroblush.png'
import talkingcaro from '../assets/images/talkingcaro.gif'
import text from '../utils/text.js'

export default {
  name: 'Caro',
  props: {
    allPresentsFound: Boolean,
  },
  data: function() {
    return {
      image: caro,
      carowithletter: carowithletter,
      talking: false,
      currentIndex: 0,
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
    readLetter: function() {
      this.$emit("readLetter")
      this.carowithletter = caroblushing
    },
    stopTalking: function() {
      if (this.currentIndex < this.text.length - 1) {
        this.currentIndex += 1
      } else {
        this.currentIndex = 0
      }
      this.talking = false
      this.image = caro
    },
  },
}
</script>
<style scoped>
.caro {
  width: 6vw;
  height: 10vw;
  top: 22vw;
  left: 31vw;
}
.letter {
  width: 6vw;
  height: 10vw;
  top: 22vw;
  left: 31vw;
  z-index: 80000;
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
  top: 12vw;
  height: 5vw;
  z-index: 8000;
  overflow-x: hidden;
  overflow-y: auto;
  width: 11.5vw;
}
</style>
