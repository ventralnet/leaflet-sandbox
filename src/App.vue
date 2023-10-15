<script>
import 'leaflet';
import 'leaflet/dist/leaflet.css'
import 'reset-css';

import FreeDraw from 'leaflet-freedraw';
import 'leaflet-draw';
import 'leaflet-draw/dist/leaflet.draw.css';

export default {
  mounted() {
    const map = L.map(this.$refs.mapEle, {
      center: [51.505, -0.09],
      zoom: 13
    });
    L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(map);

    const freeDraw = new FreeDraw();
    map.addLayer(freeDraw);

    const drawControl = new L.Control.Draw({

    });
    map.addControl(drawControl);
  },
};
</script>

<template>
  <div class="map" ref="mapEle"></div>
</template>

<style scoped>
  .map {
    height: 100vh;
    width: 100%;
    background-color: red;
  }
</style>
