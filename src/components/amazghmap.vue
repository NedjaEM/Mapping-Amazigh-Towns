<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
  <div id="map">
  </div>
    <div id="map-overlay"></div>
</template>


<script>
import * as d3 from '../../lib/d3'
import mapboxgl from "mapbox-gl"
export default {
  name: 'amazghmap',
  props: {
    msg: String
  },
  mounted() {
      mapboxgl.accessToken = 'pk.eyJ1IjoibmFkeTE5NiIsImEiOiJjazg1enF4dTAwMWowM2dwZGRtM3d6bTR5In0.Isdajp-jzePFbwz97Uqbyg';
      this.map = new mapboxgl.Map({
          container: 'map',
          style: 'mapbox://styles/nady196/ckfoaol3000do19qpv4eklijk'
      });
      this.map.on('click', 'amazigh-vill-complete', function(e) {
          console.log("hi")
          var coordinates = e.features[0].geometry.coordinates.slice();
          var description = e.features[0].properties.Village;
          console.log(coordinates);
          console.log(description);
          while (Math.abs(e.lngLat.lng - coordinates[0]) > 180) {
          coordinates[0] += e.lngLat.lng > coordinates[0] ? 360 : -360;
          }

          document.getElementById("map-overlay").innerHTML=
            "<h3>" +description+"</h3>";
      
    });
}
}
  
</script>


<style>

.mapboxgl-canvas {
    /* position: fixed!important;
    height: 80%!important;
    margin-top: 100px;
    width: 70%!important;; */

}
/* .mapboxgl-canvas {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
.map {
  position: relative;
} */

</style>
