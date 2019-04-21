<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <v-list-tile v-for="item in menuItems" :key="item.title" :to="item.link">
        <v-list-tile-content>{{ item.title }}</v-list-tile-content>
      </v-list-tile>
    </v-toolbar>

    <main>
      <router-view></router-view>
    </main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    HelloWorld
  },
  data() {
    return {
      menuItems: [
        {
          icon: "date_range",
          title: "Jobs",
          link: "/jobs"
        },
        {
          icon: "Home",
          title: "Home",
          link: "/"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
body {
  padding-top: 64px;
}
</style>
