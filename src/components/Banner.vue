<template>
  <div class="top-banner">
    <h1>Our Beers</h1>
  </div>
</template>

<style scoped>
.top-banner{
  background: center no-repeat url("../img/beer.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  opacity:0.7;
  height: 160px;
  color:white;
  padding: 9px;
  text-align: center;
  line-height: 151px;
  font-family: Poppins, sans-serif;
}
</style>

<script>
export default {
  name: "Banner",

  data: () => ({
  }),
};
</script>