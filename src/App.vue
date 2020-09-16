<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn @click="onClick()" icon class="mr-2">
        <v-avatar>
          <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
        </v-avatar>
      </v-btn>
      <div id="profile" style="display:none">
        <Login />
      </div>
      <div id="regis"></div>
    </v-app-bar>

    <v-main></v-main>
  </v-app>
</template>

<script>
import Login from "./components/Login.vue";

export default {
  name: "App",
  components: {
    Login,
  },
  methods: {
    onClick() {
      if (this.whenClick == 0) {
        document.getElementById("profile").style.display = "block";
        this.whenClick = 1;
      } else {
        document.getElementById("profile").style.display = "none";
        this.whenClick = 0;
      }
    },
    },
    onClick2() {
      if (this.dialog == false) {
        document.getElementById("regis").style.display = "block";
        this.dialog = true;
      } else {
        document.getElementById("regis").style.display = "none";
        this.dialog = false;
      }
  },

  data: () => ({
    whenClick: 0,
  }),
};
</script>
<style>
</style>