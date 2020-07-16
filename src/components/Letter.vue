<template>
    <div class="letter">
      <img class="interactive pointer" :src="pages[currentPage]" @click="showNextCard" />
      <div class="next tag" @click="show = false"></div>
    </div>
</template>
<script>
import page1 from '../assets/images/page1.png'
import page2 from '../assets/images/page2.png'
import page3 from '../assets/images/page3.png'
import page4 from '../assets/images/page4.png'
import page5 from '../assets/images/page5.png'
import page6 from '../assets/images/page6.png'
import page7 from '../assets/images/page7.png'
import page8 from '../assets/images/page8.png'

export default {
  name: 'Letter',
  data: function() {
    return {
      pages: [page1, page2, page3, page4, page5, page6, page7, page8],
      currentPage: 0,
    }
  },
  methods: {
    showNextCard: function() {
      if (this.currentPage < this.pages.length - 1) {
        this.currentPage += 1
      } else {
        this.$emit("theEnd")
      }
    },
  },
}
</script>
<style scoped>
.next {
  width: 6vw;
  height: 4vw;
  top: 29vw;
  left: 72vw;
}
.letter {
    z-index: 100000;
}
</style>
