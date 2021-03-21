<template>
<div class="app">
  <sidebar></sidebar>
  <beers></beers>
  </div>
</template>

<style>
body{
  background-color:#282320;
}
</style>

<style scoped>
.app {
display: flex;
flex-wrap: wrap;
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
    Beers
  },

  data: () => ({
    //
  }),
};
</script>