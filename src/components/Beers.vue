<template>
  <div class="beers">
      <banner></banner>
      <beer-box></beer-box>

  </div>
</template>

<style scoped>
.beers{

  min-width: 320px;
  background: #FFFFFF;
    font-family: Poppins, sans-serif;

}
</style>

<script>
import Banner from "./Banner"
import BeerBox from './BeerBox.vue';

export default {
  name: "Beers",

  components: {
    Banner,
    BeerBox
  },

  data: () => ({
  }),
  computed: {
    query: () => {
      return "";
    },
  },
};
</script>