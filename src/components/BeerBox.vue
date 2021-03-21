<template>
  <div class="beer-box">
    <img :src="picture" />
    <p>{{ name }}</p>
    <p>Alcohol content: {{ alcohol }}%</p>
    <p>Bitterness: IBU {{ bitterness }}</p>
    <p>Color: EBC {{ color }}</p>
    <p>{{ description }}</p>
  </div>
</template>

<style scoped>
.beer-box {
  display: flex;
  flex-direction: column;
  align-self: center;
  margin: 9px;
  height: 600px;
  width: 300px;
  background: white;
  color: #717171;
  padding: 9px;
  border: #717171 solid 1px;
  border-radius: 5px;
  font-family: Poppins, sans-serif;
  overflow: hidden;
}
.beer-box > p {
  margin: 5px;
}
.beer-box > p:nth-child(2) {
  font-weight: bold;
}
.beer-box > img {
  max-height: 150px;
  margin: auto;
}
</style>

<script>
export default {
  name: "BeerBox",

  props: {
    picture: { type: String, required: false },
    name: { type: String, required: true },
    alcohol: { type: Number, required: false },
    bitterness: { type: Number, required: false },
    color: { type: Number, required: false },
    description: { type: String, required: false },
  },

  data: () => ({}),
};
</script>