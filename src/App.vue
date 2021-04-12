<template>
  <v-app>
    <v-app-bar dark app dense src="https://picsum.photos/1920/1080?random">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-btn icon @click="blnSearch = !blnSearch">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-scroll-x-transition>
        <v-text-field v-show="blnSearch" hide-details></v-text-field>
      </v-scroll-x-transition>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>

      <template v-slot:extension>
        <v-row justify="center" no-gutters>
          <v-tab :to="{path:'/home'}" fab>Home</v-tab>
          <v-tab :to="{path:'/about'}" fab>About</v-tab>
          <v-tab :to="{path:'/hello'}" fab>Hello</v-tab>
        </v-row>
      </template>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    blnSearch: false,
    //
  }),
};
</script>
