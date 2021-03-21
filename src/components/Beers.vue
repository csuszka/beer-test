<template>
  <div class="beers">
      <banner></banner>

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

export default {
  name: "Beers",

  components: {
    Banner
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