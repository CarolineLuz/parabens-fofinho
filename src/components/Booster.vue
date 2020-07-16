<template>
  <div>
    <div v-if="show">
      <img class="interactive" :src="booster" v-if="!opened" @click="opened = true" />
      <img class="interactive" :src="openBooster" v-if="opened" />
      <img class="interactive pointer" :src="cards[currentCard]" v-if="opened" @click="showNextCard" />
      <div class="closing tag" @click="show = false"></div>
    </div>
    <img class="interactive" :src="tinybooster" v-if="showTinyBooster" />
    <div class="booster tag" @click="showBooster" @mouseover="showTinyBooster = true" @mouseleave="showTinyBooster = false"></div>
  </div>
</template>
<script>
import fearlessPoodle from '../assets/images/fearlesspoodle.png'
import nienkerkeSequeira from '../assets/images/nienkerkesequeira.png'
import sanctumOfTranquilForce from '../assets/images/sanctumoftranquilforce.png'
import sekasDoweredNightMage from '../assets/images/sekasdowerednightmage.png'
import feetOfLuz from '../assets/images/feetofluz.png'
import whimsicalDouro from '../assets/images/whimsicaldouro.png'
import openBooster from '../assets/images/openbooster.png'
import tinybooster from '../assets/images/tinybooster.png'
import booster from '../assets/images/booster.png'

export default {
  name: 'Booster',
  data: function() {
    return {
      image: fearlessPoodle,
      booster: booster,
      show: false,
      opened: false,
      openBooster: openBooster,
      showTinyBooster: false,
      tinybooster: tinybooster,
      cards: [sanctumOfTranquilForce, feetOfLuz, sekasDoweredNightMage, fearlessPoodle, nienkerkeSequeira, whimsicalDouro],
      currentCard: 0,
    }
  },
  methods: {
    showBooster: function() {
      this.show = true
      this.$emit('clicked')
    },
    showNextCard: function() {
      if (this.currentCard < this.cards.length - 1) {
        this.currentCard += 1
      } else {
        this.currentCard = 0
      }
    },
  },
}
</script>
<style scoped>
.booster {
  width: 6vw;
  height: 4vw;
  top: 29vw;
  left: 72vw;
}
.closing {
  width: 4vw;
  height: 4vw;
  top: 9vw;
  left: 27vw;
}
</style>
