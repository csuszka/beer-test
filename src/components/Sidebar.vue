<template>
  <div>
    <p>Alcohol content</p>
    <v-radio-group v-model="selectedAlcohol">
      <v-radio
        v-for="(alcohol, index) in alcoholLevels"
        :key="index"
        :label="alcohol.text"
        :value="index"
      />
    </v-radio-group>
    <p>Bitterness</p>
    <v-radio-group v-model="selectedBitterness">
      <v-radio
        v-for="(bitterness, index) in bitternessLevels"
        :key="index"
        :label="bitterness.text"
        :value="index"
      />
    </v-radio-group>
    <p>Color</p>
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
      let queryString = `https://api.punkapi.com/v2/beers`;
      return queryString;
    },
  },
};
</script>