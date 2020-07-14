<template>
  <div class="canvas">
    <Background />
    <Plant ref="plant" />
    <Babyoil @clicked="getMassagiVouchy" />
    <Whisky @savePlant="savePlant" />
    <Bikini @clicked="getVabaliVouchy" />
    <WOW />
    <Chair @chairdance="findLighter"/>
    <Ze ref="ze"/>

    <img :src="require('../assets/images/table.png')" />
    <img :src="require('../assets/images/sofa.png')" />
    <Caro @talking="comeToTalk" />
    <Lamps />
    <Kallax />
  </div>
</template>

<script>
import Bikini from './Bikini'
import Chair from './Chair'
import Kallax from './Kallax'
import Plant from './Plant'
import WOW from './WOW'
import Lamps from './Lamps'
import Caro from './Caro'
import Ze from './Ze'
import Babyoil from './Babyoil'
import Background from './Background'
import Whisky from './Whisky'

export default {
  name: 'Screen',
  props: {
    msg: String,
  },
  components: {
    Bikini,
    Plant,
    Kallax,
    Whisky,
    WOW,
    Chair,
    Caro,
    Ze,
    Background,
    Lamps,
    Babyoil,
  },
  methods: {
    comeToTalk: function() {
      this.$refs.ze.moveTo(38, true)
    },
    getVabaliVouchy: function() {
      this.$refs.ze.moveTo(30, true)
    },
    getMassagiVouchy:function() {
       this.$refs.ze.moveTo(43, false)
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
