<template>
  <div>
    <img class="interactive" :src="image" :style="'left:' + x + 'vw; transition: 2s'" />
    <!-- <div class="ze tag" "></div> -->
  </div>
</template>
<script>
import zeleft from '../assets/images/zeleft.png'
import zeright from '../assets/images/zeright.png'
import zewalksright from '../assets/images/zewalkingright.gif'
import zewalksleft from '../assets/images/zewalkingleft.gif'

export default {
  name: 'Ze',
  data: function() {
    return {
      image: zeleft,
      x: 50,
    }
  },
  methods: {
    faceCoordinate: function(n) {
      this.image = n < this.x ? zeleft : zeright
    },
    moveTo: function(n, faceleft) {
      this.image = n < this.x ? zewalksleft : n > this.x ? zewalksright : this.image
      let self = this
      self.x = n
      setTimeout(function() {
        self.image = faceleft ? zeleft : zeright
      }, 2000)
    },
  },
}
</script>
<style scoped>
img {
  height: 21vw;
  position: absolute;
  top: 12vw;
  width: auto;
}
.ze {
  width: 6vw;
  height: 12vw;
  top: 22vw;
  left: 41vw;
}
</style>
