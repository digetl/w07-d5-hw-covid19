<template lang="html">
 <div class=country-covid-details>
  <li class="country-name">{{country.Country}}</li>
   <button v-on:click="show-details">Show details</button>
    <button v-on:click="hide-details">Hide Details</button>
  <li v-if="true"class="country-data">Total Confirmed Cases: {{country.TotalConfirmed}}</li>
  <li class="country-data">Total Deaths: {{country.TotalDeaths}}</li>
  <li class="country-data">Total Recovered Cases: {{country.TotalRecovered}}</li>
  <li class="country-data">New Confirmed Cases: {{country.NewConfirmed}}</li>
  <li class="country-data">New Deaths: {{country.NewDeaths}}</li>
  <li class="country-data">New Recovered Cases: {{country.NewRecovered}}</li>
 </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['country'],
  methods: {

  },
    // data:() {
    //   show-details: 'false',
    //   show-details: 'true'
    // }
}
</script>

<style>
.country-name {
font-weight: 700;
font-size: 1.2rem;
}

.country-covid-details {
padding-bottom: 0.5rem;
}

</style>
