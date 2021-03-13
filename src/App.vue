<template>
  <v-app>
    <header></header>
    <router-view />
    <app-footer />
  </v-app>
</template>

<script>
import AppFooter from '@/components/Footer';

export default {
  name: 'App',
  components: {
    AppFooter,
  },
};
</script>

<style>
@import 'https://cdn.jsdelivr.net/npm/@mdi/font@5.x/css/materialdesignicons.min.css';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
