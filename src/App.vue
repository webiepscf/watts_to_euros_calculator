<template>
  <div id="app" class="container">
    <watts-to-euros-calculator />
  </div>
</template>

<script>
import WattsToEurosCalculator from "./components/WattsToEurosCalculator.vue";
export default {
  name: "App",
  components: {
    WattsToEurosCalculator,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
