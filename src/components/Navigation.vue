<template>
    <v-app-bar app color="primary" dark>
        <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer=!drawer"></v-app-bar-nav-icon>
      <div class="d-flex align-center">
        <h1 class="hidden-sm-and-down">Migraine Hospital</h1>
        <h1 class="hidden-md-and-up title-text">Migraine Hospital</h1>
      </div>

      

      <v-spacer></v-spacer>

      <v-btn class="nav-button hidden-sm-and-down"><router-link to="/">Home</router-link></v-btn>
      <v-btn class="nav-button hidden-sm-and-down"><router-link to="/about">About</router-link></v-btn>
      <v-btn class="nav-button hidden-sm-and-down"><router-link to="/contact">Contact</router-link></v-btn>

      <v-btn
        href="#"
        target="_blank"
        text
      >
        <span class="mr-2">Social Media</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
</template>

<script>
export default {
    name: "Navigation",
    data() {
        return {
            drawer: false
        }
    }
}
</script>

<style scoped>
.title-text {
    font-size: 1em;
}
a {
    text-decoration: none;
}
.nav-button {
    margin-right: 1%;
}
</style>