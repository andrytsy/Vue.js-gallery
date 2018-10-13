<template>
  <div id="app">
    <h1>Vue.js Gallery</h1>
    <!-- eslint-disable-next-line -->
    <div v-for="row in rows">
      <Gallery :data="row" />
    </div>
    <FullSize />
  </div>
</template>

<script>
import image1 from "./assets/1.jpg"
import image2 from "./assets/2.jpg"
import image3 from "./assets/3.jpg"
import image4 from "./assets/4.jpg"
import image5 from "./assets/5.jpg"
import image6 from "./assets/6.jpg"
import image7 from "./assets/7.jpg"
import image8 from "./assets/8.jpg"
import image9 from "./assets/9.jpg"
import image10 from "./assets/10.jpg"
import image11 from "./assets/11.jpg"
import image12 from "./assets/12.jpg"
import image13 from "./assets/13.jpg"
import image14 from "./assets/14.jpg"
import image15 from "./assets/15.jpg"
import image16 from "./assets/16.jpg"
import Gallery from './components/Gallery.vue'
import FullSize from './components/FullSize.vue'

export default {
  name: 'app',
  components: {
    Gallery, FullSize
  },
  data() {
    return {
      rows: [
        [
          {url: image1, id: 1, name: 'BANE NOR WAREHOUSE, Norway', width: 1066, author: 'Architect: Eder Biesel'},
          {url: image2, id: 2, name: 'OPERAGATA 20, NO', width: 888, author: 'Client: Skanska'},
          {url: image3, id: 3, name: '401 WEST GEORGIA STREET, Vancouver', width: 750, author: 'Architect: B+H Architects'},
          {url: image4, id: 4, name: '401 WEST GEORGIA STREET, Vancouver', width: 749, author: 'Architect: B+H Architects'},
          {url: image5, id: 5, name: 'SKAUN UNGDOMSSKOLE',  width: 705, author: 'Architect: HUS Arkitekter'},
          {url: image6, id: 6, name: 'SUSSEX UNIVERSITY, UK', width: 888, author: 'Architect: Howkins/Brown'},
          {url: image7, id: 7, name: 'HANGZHOU TOWER', width: 500, author: 'Architect: SOM'},
          {url: image8, id: 8, name: 'AMAZON\'S SEAPORT OFFICE', width: 400, author: 'Architect: Gensler'}
        ],
        [
          {url: image9, id: 9, name: 'SMITHSONIAN CAMPUS MASTER PLAN', width: 1000, author: 'Architect: BIG'},
          {url: image10, id: 10, name: 'RICHARDSON INNOVATION CENTER', width: 888, author: 'Client: Number Ten'},
          {url: image11, id: 11, name: 'CHILDREN HOSPITAL, Copenhagen', width: 1067, author: 'Architect: BIG'},
          {url: image12, id: 12, name: 'JORDAN AMFI ICE HOCKEY ARENA, Oslo', width: 888, author: 'Architect: Link Arkitektur AS'},
          {url: image13, id: 13, name: 'LBF TOWER', width: 535, author: 'Architect: Snohetta'},
          {url: image14, id: 14, name: 'KNUD HOLMS GATE', width: 416, author: 'Architect: Eder Biesel'},
          {url: image15, id: 15, name: 'University at the Niagara Falls', width: 599},
          {url: image16, id: 16, name: 'VR – Diridon', width: 888, author: 'Architect: Gensler'}
        ]
      ]
    }
  }
}
</script>

<style>
@font-face {
  font-family: "HelveticaNeueUltraLight";  
  src: url("./assets/fonts/HelveticaNeue-UltraLight.svg") format("svg"),
  url("./assets/fonts/HelveticaNeue-UltraLight.woff") format("woff"), 
  url("./assets/fonts/HelveticaNeue-UltraLight.ttf") format("truetype"); 
  font-style: normal; 
  font-weight: normal;
}

h1 {
  margin: 20px 0px 0px;
}

#app, footer {
  font-family: 'Avenir', 'HelveticaNeueUltraLight', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #eeeeee;
}

#logo {
  width: 100px;
}

html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  background-color: #1c1c1c;
}

footer {
  margin-bottom: 20px;
  font-weight: 800;
}

a {
  color: rgb(122, 137, 207);
}
</style>
