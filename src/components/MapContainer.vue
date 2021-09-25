<template>
  <div class="row map">
    <LMap :zoom="zoom" :maxZoom="maxZoom" :center="center">
      <LTileLayer url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png" />
      <LMarker
        v-for="stop in stops"
        :key="stop.stop_id"
        :lat-lng="[stop.stop_lat, stop.stop_lon]"
        @click="showData(stop.stop_lat, stop.stop_lon)"
      />
    </LMap>
  </div>
</template>

<script>
import { LMap, LMarker, LTileLayer } from "@vue-leaflet/vue-leaflet";
import "leaflet/dist/leaflet.css";
import stops from "../assets/stops.json";

export default {
  name: "MapContainer",
  components: {
    LMap,
    LTileLayer,
    LMarker,
  },
  data() {
    return {
      zoom: 15,
      maxZoom: 18,
      center: [-5.824846031399589, -35.21261114066273],
      stops: stops.slice(0, 50),
    };
  },
  created() {
    console.log(this.stops.length);
  },
  methods: {
    async showData(lat, lng) {
      console.log(lat, lng);
      const response = await fetch(
        `https://nominatim.openstreetmap.org/reverse?lat=${lat}&lon=${lng}&format=json`
      );
      const data = await response.json();
      console.log(data);
    },
  },
};
</script>

<style scoped>
.map {
  height: 80vh;
}

@media (max-width: 576px) {
  .map {
    height: 65vh;
  }
}
</style>
