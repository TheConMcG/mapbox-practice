<template>
  <div class="home">
    <div id="map" style='width: 600px; height: 400px'></div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import mapboxgl from 'mapbox-gl'; // or "const mapboxgl = require('mapbox-gl');"

export default {
  data: function () {
    return {
      map: [],
    };
  },
  name: 'Home',
  components: {
    HelloWorld
  },
  mounted: function () {
    this.generateMap();
  },
  methods: {
    generateMap: function() {
      mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_KEY;
      const map = new mapboxgl.Map({
        container: 'map', // container ID
        style: 'mapbox://styles/mapbox/streets-v11', // style URL
        center: [-74.5, 40], // starting position [lng, lat]
        zoom: 9 // starting zoom
      })
    }
  }
}
</script>
