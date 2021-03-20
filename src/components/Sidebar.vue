<template>
  <div>
    <p>Alcohol content</p>
    <v-checkbox
      v-for="(percent, index) in alcohol"
      :key="index"
      :label="percent.text"
      v-model="percent.value"
    ></v-checkbox>
    <p>Bitterness</p>
    <p>Color</p>
  </div>
</template>

<script>
export default {
  name: "Sidebar",

  data: () => ({
    alcohol: [
      { text: "non-alcoholic - 0%", value: false },
      { text: "low - 0-4%", value: false },
      { text: "medium - 4-8%", value: false },
      { text: "high - >8%", value: false },
    ],
    bitterness: [
      { text: "low - IBU 0-40", value: false },
      { text: "medium - IBU 40-80", value: false },
      { text: "high IBU 80-120", value: false },
    ],
    color: [
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