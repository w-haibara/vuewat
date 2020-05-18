<template>
  <v-app>
    <v-app-bar app color="primary" dark></v-app-bar>

    <WatToWasm />
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
