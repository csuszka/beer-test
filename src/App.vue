<template>
  <div class="app">
    <sidebar @changed-query="updateBeers"></sidebar>
    <beers :beers="beers"></beers>
  </div>
</template>

<style>
body {
  background-color: #717171;
}
</style>

<style scoped>
.app {
  margin: auto;
  display: flex;
  min-width: 320px;
  max-width: 1280px;
}
</style>

<script>
import Sidebar from "./components/Sidebar";
import Beers from "./components/Beers";

export default {
  name: "App",

  components: {
    Sidebar,
    Beers,
  },

  data: () => ({
    beers: null,
  }),
  methods: {
    updateBeers: function (beersData) {
      this.beers = beersData;
    },
  },
};
</script>