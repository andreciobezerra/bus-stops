<template>
  <MapContainer />
  <br />
  <Infos />
</template>

<script>
import Infos from "./components/Infos.vue";
import MapContainer from "./components/MapContainer.vue";
import "bootstrap/dist/css/bootstrap.css";

export default {
  name: "App",
  components: {
    MapContainer,
    Infos,
  },
};
</script>

<style>
#app {
  padding: 15px 30px;
  background-color: #f1f1f1;
  height: 100vh;
}
</style>
