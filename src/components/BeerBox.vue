<template>
  <div class="beer-box">
    <img :src="picture" />
    <p>{{ name }}</p>
    <p>Alcohol content: {{alcohol}}%</p>
    <p>Bitterness: IBU {{bitterness}}</p>
    <p>Color: EBC {{color}}</p>
    <p>{{ description }}</p>
  </div>
</template>

<style scoped>
.beer-box {
  display: flex;
  flex-direction: column;
  align-self: center;
  margin: 5px;
  height: 600px;
  width: 300px;
  background: white;
  color: #717171;
  padding: 9px;
  border: #717171 solid 1px;
  border-radius: 5px;
  font-family: Poppins, sans-serif;
  text-overflow: ellipsis;
}
.beer-box>p{
  margin: 5px;
}
.beer-box>p:nth-child(2) {
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

  data: () => ({
        picture: "https://images.punkapi.com/v2/83.png",
        name: "India Session Lager - Prototype Challenge",
alcohol: 5,
bitterness: 4,
color: 45,
    description:
      "A potently bitter hop variety originally grown in the US around 40 years ago, Comet has been newly resurrected - this German version has bold resinous grapefruit flavours, which add a huge fresh hop aroma to this IPA.",
    
  }),
};
</script>