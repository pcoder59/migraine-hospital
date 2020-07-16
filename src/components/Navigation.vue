<template>
    <div>
        <v-navigation-drawer app v-model="drawer" class="blue lighten-2 nav-drawer" disable-resize-watcher>
            <v-list>
              <template v-for="(item,index) in items">
                  <v-list-item :key="index">
                      <v-list-item-content style="padding:10%; font-size:1.5em">
                          <router-link :to="item.link">
                            {{item.title}}
                          </router-link>
                      </v-list-item-content>
                  </v-list-item>
                  <v-divider :key="`divider-${index}`" color="black"></v-divider>
              </template>
          </v-list>
        </v-navigation-drawer>
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
    </div>
</template>

<script>
export default {
    name: "Navigation",
    data() {
        return {
            drawer: false,
            items: [
                {
                    title: "Home",
                    link: "/"
                },
                {
                    title: "About",
                    link: "/about"
                },
                {
                    title: "Contact",
                    link: "/contact"
                },
            ],
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