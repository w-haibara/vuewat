<template>
  <v-app>
    <v-app-bar app color="primary" dark></v-app-bar>

    <WatToWasm class="page" />
  </v-app>
</template>

<script>
import WatToWasm from "./components/WatToWasm";

export default {
  name: "App",

  components: {
    WatToWasm
  },

  data: () => ({
    //
  })
};
</script>

<style scoped>
.page {
  height: 100vh;
  overflow: scroll;
  -ms-overflow-style: none; /* for IE, Edge */
  scrollbar-width: none; /* for Firefox */
}
.page::-webkit-scrollbar {
  /* forChrome, Safari */
  display: none;
}
</style>

<style>
.background {
  background: #abbaab; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #ffffff,
    #abbaab
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #ffffff,
    #abbaab
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
</style>