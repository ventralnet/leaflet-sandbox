<script>
import 'leaflet';
import 'leaflet/dist/leaflet.css'
import 'reset-css';

export default {
  mounted() {
    const map = L.map(this.$refs.mapEle, {
      center: [51.505, -0.09],
      zoom: 1
    });
    L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
      noWrap: true,
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(map);
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
