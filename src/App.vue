<template>
  <v-app>
    <!--Navigation Module-->
    <v-app-bar app color="primary" dark>
      <v-tool-bar-title>Vuetify Dashboard</v-tool-bar-title>
      <v-spacer></v-spacer>
      <v-btn text rounded>Home</v-btn>
      <v-btn text rounded>Login</v-btn>
    </v-app-bar>
    <v-content>
      <router-view></router-view>
    </v-content>
    <!--Footer Module-->
    <v-footer
        color="primary lighten-1"
        padless
    >
      <v-row
          justify="center"
          no-gutters
      >
        <v-btn
            v-for="link in links"
            :key="link"
            color="white"
            text
            rounded
            class="my-2"
        >
          {{ link }}
        </v-btn>
        <v-col
            class="primary lighten-2 py-4 text-center white--text"
            cols="12"
        >
          {{ new Date().getFullYear() }} <strong>Vuetify Dashboard</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  data() {
    return {
      links: [
      'Home',
      'Login'
    ]}
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
