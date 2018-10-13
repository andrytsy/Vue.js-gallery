<template>
  <div @click="fullSizeOff" class="full-size" :class="{ 'active': fullSizeMode }">
    <img :src="imageSrc">
  </div>
</template>

<script>
import Bus from '../utils/bus.js'
export default {
  props: ['data'],
  data() {
    return {
      imageSrc: '',
      fullSizeMode: false
    }
  },
  methods: {
    fullSizeOff() {
      this.imageSrc = '';
      this.fullSizeMode = false;
    }
  },
  mounted() {
    Bus.$on('fullSizeModeOn', (src) => {
      this.imageSrc = src;
      this.fullSizeMode = true;
    })
  }
}
</script>

<style scoped>
.full-size {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(8, 14, 43, 0.4);
  transition: 0.5s;
  opacity: 0;
  z-index: 0;
}

.full-size.active {
  transition: 0.5s;
  opacity: 10;
  z-index: 10;
}

.full-size.active img {
  z-index: 11;
}
</style>
