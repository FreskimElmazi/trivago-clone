<template>
  <div id="app">
    <home-page />
  </div>
</template>

<script>
import HomePage from "./pages/home-page.vue";

export default {
  name: "App",
  components: {
    HomePage,
  },
};
</script>

<style>
#app {
  font-family: Proxima Vara, Arial, Helvetica, Sans, Sans-Serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
