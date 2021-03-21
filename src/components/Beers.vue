<template>
  <div class="beers">
    <banner></banner>
    <div v-if="!beers.length" class ="no-available-beer"><h1>Sorry, no such beers on our list :(</h1></div>
    <div v-else class="available-beers">
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
  min-width: 960px;
  background: #ffffff;
  font-family: Poppins, sans-serif;
}

.no-available-beer{
  color: #717171;
  text-align: center;
  line-height: 50vh;
}

.available-beers{
  display: flex;
  flex-wrap: wrap;
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