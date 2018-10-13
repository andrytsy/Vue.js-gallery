<template>
  <div class="gallery">
    <!-- eslint-disable-next-line -->
    <div class="image" @click="fullSize(image.url)" @mouseover="expand(image)" @mouseleave="rollUp(image)" :id="image.id" v-for="image in data">
      <div class="image__info">
        <h3>{{image.name}}</h3>
        <span>{{image.author}}</span>
      </div>
      <img :src="image.url">
    </div>
  </div>
</template>

<script>
import Bus from '../utils/bus.js'

export default {
  props: ['data'],
  data() {
    return {
      current: 0,
      fullSizeMode: false
    }
  },
  methods: {
    fullSize(src) {
      Bus.$emit('fullSizeModeOn', src);
    },
    expand(img) {
      this.current = img.id;
      var elem = document.getElementById(img.id);
      elem.style.width = img.width + 'px';
    },
    rollUp(img) {
      this.current = img.id;
      var elem = document.getElementById(img.id);
      elem.style.width = '200px';
    }
  }
}
</script>

<style scoped>
h3 {
  font-size: 20px;
  margin: 0px 0px 5px 0px;
}

.gallery {
  display: grid;
  grid-template-columns: repeat(8, 2fr);
  grid-auto-flow: row dense;
  overflow: hidden;
  padding: 15px;
}

.image {
  z-index: 1;
  position: relative;
  overflow: hidden;
  width: 200px;
  height: 450px;
  -webkit-transition: 0.5s;
  transition: 0.5s;
  box-shadow: -5px 0px 20px black;
  margin: 0 auto;
}

.image:hover {
  transition: 0.5s;
  -webkit-transition: 0.5s;
}

.image__info {
  position: absolute;
  width: 100%;
  top: 0px;
  left: 0px;
  padding: 10px;
  opacity: 0;
  text-align: left;
  text-transform: uppercase;
  transition: 3s;
  color: #ffffff;
  text-shadow: 1px 1px 5px black;
  background-color: rgba(0, 0, 0, 0.1);
}

.image__info span {
  font-size: 16px;
}

.image:hover .image__info {
  opacity: 1;
  transition: 3s;
}

.image img {
  height: 500px;
  -webkit-filter: grayscale(100%); /* Safari 6.0 - 9.0 */
  filter: grayscale(100%);
  transition: 0.5s;
}

.image:hover img {
  -webkit-filter: none; /* Safari 6.0 - 9.0 */
  filter: none;
  transition: 0.5s;
}
</style>
