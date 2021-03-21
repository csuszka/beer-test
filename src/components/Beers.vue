<template>
  <div class="beers">
    <banner></banner>
    <div v-if="!beers.length"><p>Sorry, no such beers on our list :(</p></div>
    <div v-else>
      <beer-box
        v-for="(beer, index) in beers"
        :key="index"
        :picture="beer.image_url"
        :name="beer.name"
        :alcohol="beer.abv"
        :bitterness="beer.ibu"
        :color="beer.ebc"
        :description="beer.description"
      ></beer-box>
    </div>
  </div>
</template>

<style scoped>
.beers {
  min-width: 100vmin;
  background: #ffffff;
  font-family: Poppins, sans-serif;
}
</style>

<script>
import Banner from "./Banner";
import BeerBox from "./BeerBox.vue";

export default {
  name: "Beers",

  components: {
    Banner,
    BeerBox,
  },

  props: {
    beers: {
      type: Array,
      required: true,
    },
  },

  data: () => ({}),
};
</script>