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
    <v-radio-group v-model="selectedColor">
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
  background: #f6f6f6;
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
    selectedColor: 0,
    colors: [
      { text: "All", value: false },
      { text: "light - EBC 0-20", value: false },
      { text: "medium - EBC 20-40", value: false },
      { text: "dark - EBC 40+", value: false },
    ],
    selectedName: "",
    rules: [],
    getDataSettings: {
      method: "GET",
      headers: {
        Accept: "application/json",
        "Content-Type": "application/json",
      },
    },
  }),
  computed: {
    query() {
        let queryString = `https://api.punkapi.com/v2/beers?page=1&per_page=15`;

        switch (this.selectedAlcohol) {
          case 0:
            queryString += "";
            break;
          case 1:
            queryString += "&abv_lt=0.05";
            break;
          case 2:
            queryString += "&abv_gt=0.049&abv_lt=4.001";
            break;
          case 3:
            queryString += "&abv_gt=3.999&abv_lt=8.001";
            break;
          case 4:
            queryString += "&abv_gt=7.999";
            break;
        }

        switch (this.selectedBitterness) {
          case 0:
            queryString += "";
            break;
          case 1:
            queryString += "&ibu_lt=40.001";
            break;
          case 2:
            queryString += "&abv_gt=39.999&abv_lt=80.001";
            break;
          case 3:
            queryString += "&abv_gt=79.999";
            break;
        }

        switch (this.selectedColor) {
          case 0:
            queryString += "";
            break;
          case 1:
            queryString += "&ebc_lt=20.001";
            break;
          case 2:
            queryString += "&ebc_gt=19.999&ebc_lt=40.001";
            break;
          case 3:
            queryString += "&ebc_gt=39.999";
            break;
        }
        console.log(queryString);
        return queryString;
    },
  },
  watch: {
    query: {
      async handler (val, oldVal) {
        const beersData = await this.getData(val);
        this.$emit("changed-query", beersData);
      },
      immediate: true,
    },
  },
  methods: {
    async getData(queryString) {
      const fetchResponse = await fetch(queryString, this.getDataSettings);
      const data = await fetchResponse.json();
      console.log(data);
      return data;
    },
  },
};
</script>