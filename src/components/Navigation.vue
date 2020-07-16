<template>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <h1 class="hidden-sm-and-down">Migraine Hospital</h1>
        <h1 class="hidden-md-and-up title-text">Migraine Hospital</h1>
      </div>

      <v-spacer></v-spacer>

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
    
}
</script>

<style scoped>
.title-text {
    font-size: 1em;
}
</style>