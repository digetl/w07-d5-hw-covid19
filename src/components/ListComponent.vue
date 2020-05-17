<template lang="html">
 <div class=country-covid-details>
  <li class="country-name">{{country.Country}}</li>
  <li>Total Confirmed Cases: {{country.TotalConfirmed}}</li>
  <li>Total Recovered Cases: {{country.TotalRecovered}}</li>
 </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['country'],
  methods: {

  }
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
