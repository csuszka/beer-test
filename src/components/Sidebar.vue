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
  </div>
</template>

<script>
export default {
  name: "Sidebar",

  data: () => ({
    selectedAlcohol: null,
    alcoholLevels: [
      { text: "non-alcoholic - 0%", value: false },
      { text: "low - 0-4%", value: false },
      { text: "medium - 4-8%", value: false },
      { text: "high - >8%", value: false },
    ],
    selectedBitterness: null,
    bitternessLevels: [
      { text: "low - IBU 0-40", value: false },
      { text: "medium - IBU 40-80", value: false },
      { text: "high IBU 80-120", value: false },
    ],
    selectedColors: null,
    colors: [
      { text: "light - EBC 0-20", value: false },
      { text: "medium - EBC 20-40", value: false },
      { text: "dark - EBC 40-80", value: false },
    ],
  }),
  computed: {
    query: () => {
      return "";
    },
  },
};
</script>