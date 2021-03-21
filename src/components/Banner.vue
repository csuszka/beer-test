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
  max-height: 300px;
  min-height: 200px;
  color:beige;
  padding: 9px;
  text-align: center;
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