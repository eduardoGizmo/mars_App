<template>
  <div id="app">

    <section class="main-container">

      <div class="filterSide">
        <span class="version">APP VERSION 1.0.0</span>
            <h1>Mars Missions. <br/>Pictures Archive.</h1>
            <filter-values></filter-values>
            <rover-details :gallery="gallery" v-if="gallery.length"></rover-details>
            <!-- <img class="panel-rover" src="img/rover2.png"> -->
      </div>
      <div class="gallerySide">
            <gallery :gallery="gallery" />
      </div>
    </section>
  </div>
</template>

<script>
import Gallery from './components/Gallery.vue'
import Filter from './components/Filter.vue'
import RoverDetails from './components/RoverDetails.vue'
import { eventBus } from './main.js'

export default {
  name: 'app',
  components: {
    "gallery": Gallery,
    "filter-values": Filter,
    "rover-details": RoverDetails,
  },
  data(){
    return{
      gallery: [],
      selectedRover: null
    }
  },
  mounted(){
    // this.filterAPI("spirit")

    eventBus.$on('roverSelected', (data) => {
        this.filterAPI(data);
        this.selectedRover = data;
    })

  },
  methods: {
    filterAPI(selectedRover){
      fetch(`https://api.nasa.gov/mars-photos/api/v1/rovers/${selectedRover}/photos?sol=111&api_key=aHxlzf9ePoG8zvan4c7m482bM6Tvb0J5gwJsgpMS`)
      .then(res => res.json())
      .then(data => this.gallery = data.photos)
    }

  },
}
</script>
