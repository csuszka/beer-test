<template>
<div>
  <sidebar></sidebar>
  <beers></beers>
  </div>
</template>

<script>
import Sidebar from "./components/Sidebar";
import Beers from "./components/Beers";

export default {
  name: "App",

  components: {
    Sidebar,
    Beers
  },

  data: () => ({
    //
  }),
};
</script>