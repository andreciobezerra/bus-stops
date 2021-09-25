<template>
  <div class="row">
    <div class="col-md-3 d-flex justify-content-center">
      <img
        id="logo"
        src="../assets/mobby-logo.svg"
        class="rounded"
        alt="Mobby"
      />
    </div>
    <div class="col-md-9 border border-dark">{{ example.road }}</div>
  </div>
</template>

<script>
export default {
  name: "Infos",
  data() {
    return {
      example: {
        road: "Avenida",
      },
    };
  },
};
</script>

<style scoped>
#logo {
  width: 200px;
  height: 100px;
  margin-bottom: 15px;
}

@media (max-width: 768px) {
  #logo {
    width: 150px;
    height: 100px;
  }
}

@media (max-width: 576px) {
  #logo {
    width: 100px;
    height: 60px;
  }
}
</style>
