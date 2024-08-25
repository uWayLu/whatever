<template>
  <v-app>
    <!-- <app-bar /> -->
    <v-container id="router-view">
      <router-view />
    </v-container>
    <!-- <app-footer /> -->
  </v-app>
</template>

<script>
// import AppBar from '@/components/AppBar.vue'
// import AppFooter from '@/components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    // AppBar,
    // AppFooter
  }
}
</script>

<style>
@import 'https://cdn.jsdelivr.net/npm/@mdi/font@5.x/css/materialdesignicons.min.css';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}

#router-view {
  max-width: 1200px;
}
</style>
