<template>
  <v-app>
    <Navigation />
    <HeadComponent />

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
import Navigation from "./components/Navigation";
import HeadComponent from "./components/HeadComponent";

export default {
  name: "App",

  components: {
    Navigation,
    HeadComponent
  },

  data: () => ({
    //
  })
};
</script>
