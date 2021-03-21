<template>
  <div class="beer-box">
    <img v-if="picture" :src="picture" />
    <img v-else src="../img/beer-placeholder.jpg"/>
    <div>{{ name }}</div>
    <div>Alcohol content: {{ alcohol }}%</div>
    <div>Bitterness: IBU {{ bitterness }}</div>
    <div>Color: EBC {{ color }}</div>
    <div>{{ description }}</div>
  </div>
</template>

<style scoped>
.beer-box {
  margin: 10px;
  height: 600px;
  width: 300px;
  background: white;
  color: #717171;
  padding: 9px;
  border: #f6f6f6 solid 1px;
  box-shadow: 3px 3px 5px #f6f6f6;
  border-radius: 5px;
  font-family: Poppins, sans-serif;
}
.beer-box > div {
  white-space: normal;
  overflow: hidden;
  text-overflow: ellipsis;
  padding: 5px;
}
.beer-box > div:nth-child(2) {
  font-weight: bold;
  margin-top: 25px;
}
.beer-box > div:last-child {
  display: -webkit-box;
  -webkit-line-clamp: 9;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.beer-box > img {
  max-height: 150px;
  margin: auto;
  display: block;
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