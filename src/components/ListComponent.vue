<template lang="html">
 <div class=country-covid-details>
  <li class="country-name">{{country.Country}}</li>
   <button v-on:click="showdetailsClick">Show details</button>
   <button v-on:click="hidedetailsClick">Hide Details</button>

    <li v-if="showdetails">Total Confirmed Cases: {{country.TotalConfirmed}}</li>
    <li v-if="showdetails">Total Deaths: {{country.TotalDeaths}}</li>
    <li v-if="showdetails">Total Recovered Cases: {{country.TotalRecovered}}</li>
    <li v-if="showdetails">New Confirmed Cases: {{country.NewConfirmed}}</li>
    <li v-if="showdetails">New Deaths: {{country.NewDeaths}}</li>
    <li v-if="showdetails">New Recovered Cases: {{country.NewRecovered}}</li>
 </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: {
    country: Object,
    showdetails: Boolean
    },
  methods: {
    showdetailsClick: function(){
        this.showdetails = true;        
    },

    hidedetailsClick: function(){
    this.showdetails = false;        
    }


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
