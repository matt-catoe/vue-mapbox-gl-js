<template>
  <div id="map" />
</template>

<script>
import mapboxgl from "mapbox-gl";

export default {
  name: "Map",
  methods: {
    initializeMap() {
      try {
        mapboxgl.accessToken = process.env.VUE_APP_MAP_ACCESS_TOKEN;
        this.map = new mapboxgl.Map({
          container: "map",
          style: "mapbox://styles/mapbox/outdoors-v11",
          center: [9.240184722799995, 45.997446529216944],
          zoom: 10,
          pitch: 0,
          bearing: 0,
        });
      } catch (err) {
        console.log("Error initializing map", err);
      }
    },
  },
  mounted() {
    this.initializeMap();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#map {
  width: 100vw;
  height: 100vh;
}
</style>
