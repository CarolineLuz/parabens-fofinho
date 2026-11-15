<template>
  <div class="canvas">
    <Background />
    <Plant ref="plant" @plantDied="wWhiskyClickable=true"/>
    <Babyoil @clicked="getMassagiVouchy" />
    <Whisky @savePlant="savePlant" :wWhiskyClickable="wWhiskyClickable"/>
    <Bikini @clicked="getVabaliVouchy" />
    <WOW v-if="!showLetter"/>
    <Chair @chairdance="findLighter" v-if="!showLetter"/>
    <Ze ref="ze"/>
    <img :src="tableImg" />
    <img :src="sofaImg" />
    <Caro @talking="comeToTalk" @readLetter="readLetter" :allPresentsFound="allFound"/>
    <Lamps />
    <Ciggies @found="getHappyAboutCiggies" />
    <Kallax @found="foundWrappedPresent" v-if="!showLetter"/>
    <Booster @clicked="boosterFound = true" v-if="!showLetter"/>
    <Letter @theEnd="theEnd" v-if="showLetter" />
  </div>
</template>

<script>
import tableImg from '../assets/images/table.png'
import sofaImg from '../assets/images/sofa.png'
import Bikini from './Bikini.vue'
import Chair from './Chair.vue'
import Kallax from './Kallax.vue'
import Booster from './Booster.vue'
import Plant from './Plant.vue'
import WOW from './WOW.vue'
import Lamps from './Lamps.vue'
import Caro from './Caro.vue'
import Ze from './Ze.vue'
import Babyoil from './Babyoil.vue'
import Ciggies from './Ciggies.vue'
import Background from './Background.vue'
import Letter from './Letter.vue'
import Whisky from './Whisky.vue'

export default {
  name: 'Screen',
  props: {
    msg: String,
  },
  data: function(){
    return {
      boosterFound: false,
      vabaliFound: false,
      massageFound: false,
      presiFound: false,
      ciggiesFound: false,
      showLetter: false,
      wWhiskyClickable: false,
      tableImg,
      sofaImg
    }
  },
  computed: {
    allFound: function() {
    return (this.ciggiesFound && this.vabaliFound && this.massageFound && this.presiFound && this.boosterFound)
    }
  },
  components: {
    Bikini,
    Plant,
    Kallax,
    Whisky,
    WOW,
    Chair,
    Letter,
    Caro,
    Ciggies,
    Ze,
    Background,
    Lamps,
    Babyoil,
    Booster
  },
  methods: {
    theEnd: function() {
      this.$emit("theEnd")
    },
    readLetter: function() {
      this.$refs.ze.moveTo(36, true)
      this.showLetter = true;
    },
    getHappyAboutCiggies: function() {
      this.ciggiesFound = true;
      this.$refs.ze.faceCoordinate(37)
    },
    foundWrappedPresent: function() {
      this.presiFound = true;
      this.$refs.ze.faceCoordinate(80)
    },
    comeToTalk: function() {
      this.$refs.ze.moveTo(38, true)
    },
    getVabaliVouchy: function() {
      this.vabaliFound = true;
      this.$refs.ze.moveTo(21, false)
    },
    getMassagiVouchy:function() {
      this.massageFound = true;
       this.$refs.ze.moveTo(60, true)
    },
    findLighter: function() {
      let self = this;
      setTimeout(function(){
        self.$refs.ze.moveTo(57, false)
      },1000)
    },
    savePlant: function() {
      this.$refs.plant.live()
      this.$refs.ze.moveTo(10, true)
    },
  },
}
</script>
<style>
img {
  position: absolute;
  top: 0;
  width: 100%;
  left: 0;
}
.canvas {
  width: 80vw;
  position: relative;
  margin: auto;
  background: pink;
  top: 2vw;
}
</style>
