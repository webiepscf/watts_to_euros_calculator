<template>
  <div class="card" style="width: 20rem; margin: 2em auto">
    <h5 class="card-header text-center">Watts To Euros Calculator</h5>

    <div class="card-body">
      <input type="number" min="0" v-model="watts" /> Watts<br />
      <input type="range" v-model="hours" min="0" max="24" />
      {{ hours }} hours/day usage<br />
      <input type="number" v-model="days" min="0" /> days usage<br />
      <input type="number" min="0" step=".01" v-model="unitPrice" /> €/kwh [BE]
    </div>

    <div class="card-body">
      <h2 class="card-title text-center">TOTAL: {{ priceTotal }} €</h2>
    </div>

    <ul class="list-group list-group-flush">
      <li class="list-group-item">
        {{ kwhPerDay }} kWh/Day | {{ pricePerDay }} €/Day
      </li>
      <li class="list-group-item">
        {{ kwhPerYear }} kWh/Year | {{ pricePerYear }} €/Year
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      watts: 100,
      hours: 1,
      days: 1,
      unitPrice: 0.309,
    };
  },
  computed: {
    kwhPerDay() {
      return ((this.watts * this.hours) / 1000).toFixed(2);
    },
    kwhPerYear() {
      return (this.kwhPerDay * 365).toFixed(2);
    },
    priceTotal() {
      return (this.kwhPerDay * this.days * this.unitPrice).toFixed(2);
    },
    pricePerDay() {
      return (this.kwhPerDay * this.unitPrice).toFixed(2);
    },
    pricePerYear() {
      return (this.pricePerDay * 365).toFixed(2);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input {
  margin: 0.5em 0;
}
</style>
