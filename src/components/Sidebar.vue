<template>
  <div class="sidebar">
    <h2>Alcohol content</h2>
    <v-radio-group v-model="selectedAlcohol">
      <v-radio
        v-for="(alcohol, index) in alcoholLevels"
        :key="index"
        :label="alcohol.text"
        :value="index"
      />
    </v-radio-group>
    <h2>Bitterness</h2>
    <v-radio-group v-model="selectedBitterness">
      <v-radio
        v-for="(bitterness, index) in bitternessLevels"
        :key="index"
        :label="bitterness.text"
        :value="index"
      />
    </v-radio-group>
    <h2>Color</h2>
    <v-radio-group v-model="selectedColors">
      <v-radio
        v-for="(color, index) in colors"
        :key="index"
        :label="color.text"
        :value="index"
      />
    </v-radio-group>
     <v-text-field
      label="Name of the beer"
      :rules="rules"
      hide-details="auto"
      v-model="selectedName"
    ></v-text-field>
  </div>
</template>

<style scoped>
.sidebar {
  background: #F6F6F6;
  color: #717171;
  min-width: 200px;
  max-width: 320px;
  padding: 8px;
  font-family: Poppins, sans-serif;
}
</style>

<script>
export default {
  name: "Sidebar",

  data: () => ({
    selectedAlcohol: 0,
    alcoholLevels: [
      { text: "All", value: false },
      { text: "non-alcoholic - 0%", value: false },
      { text: "low - 0-4%", value: false },
      { text: "medium - 4-8%", value: false },
      { text: "high - 8%+", value: false },
    ],
    selectedBitterness: 0,
    bitternessLevels: [
      { text: "All", value: false },
      { text: "low - IBU 0-40", value: false },
      { text: "medium - IBU 40-80", value: false },
      { text: "high IBU 80+", value: false },
    ],
    selectedColors: 0,
    colors: [
      { text: "All", value: false },
      { text: "light - EBC 0-20", value: false },
      { text: "medium - EBC 20-40", value: false },
      { text: "dark - EBC 40+", value: false },
    ],
    selectedName: "",
    rules: []
  }),
  computed: {
    query: () => {
      let queryString = `https://api.punkapi.com/v2/beers?page=1&per_page=15`;
      return queryString;
    },
  },
};
</script>