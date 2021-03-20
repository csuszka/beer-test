<template>
  <div>
    <p>Alcohol content</p>
    <v-checkbox
      hide-details
      v-for="(alcohol, index) in alcoholLevels"
      :key="index"
      :label="alcohol.text"
      v-model="alcohol.value"
    />
    <p>Bitterness</p>
    <v-checkbox
      hide-details
      v-for="(bitterness, index) in bitternessLevels"
      :key="index"
      :label="bitterness.text"
      v-model="bitterness.value"
    />
    <p>Color</p>
    <v-checkbox
      hide-details
      v-for="(color, index) in colors"
      :key="index"
      :label="color.text"
      v-model="color.value"
    />
  </div>
</template>

<script>
export default {
  name: "Sidebar",

  data: () => ({
    alcoholLevels: [
      { text: "non-alcoholic - 0%", value: false },
      { text: "low - 0-4%", value: false },
      { text: "medium - 4-8%", value: false },
      { text: "high - >8%", value: false },
    ],
    bitternessLevels: [
      { text: "low - IBU 0-40", value: false },
      { text: "medium - IBU 40-80", value: false },
      { text: "high IBU 80-120", value: false },
    ],
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