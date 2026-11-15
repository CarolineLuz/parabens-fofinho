<template>
  <div>
    <img :src="backgroundImg" />
    <img :src="rugImg" />
    <img :src="drumsImg" />
  </div>
</template>
<script>
import backgroundImg from '../assets/images/background.png'
import rugImg from '../assets/images/rug.png'
import drumsImg from '../assets/images/drums.png'
export default {
  name: 'Background',
  data: function() {
    return { backgroundImg, rugImg, drumsImg }
  },
}
</script>
