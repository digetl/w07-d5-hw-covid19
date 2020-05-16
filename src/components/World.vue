<template>
<div>

<div class="container">
      <h1>World data on component</h1>
        <ul>
          <!-- <li v-for="(country, index) in countryData" :country="country" :key="index"></li> -->
          <!-- <li>New Confirmed Cases: {{globalData.NewConfirmed.toLocaleString()}}</li>
          <li>New Deaths: {{globalData.NewDeaths.toLocaleString()}}</li>
          <li>New Recovered: {{globalData.NewRecovered.toLocaleString()}}</li>
          <li>Total Confirmed Cases: <strong>{{globalData.TotalConfirmed.toLocaleString()}}</strong></li>
          <li>Total Deaths: {{globalData.TotalDeaths.toLocaleString()}}</li>
          <li>Total Recovered: <strong>{{globalData.TotalRecovered.toLocaleString()}}</strong></li> -->

        </ul>
    </div>

</div>
  
</template>

<script>
import { eventBus } from '../main.js'


export default {
  name: "world-component",

  methods: {

   
  }

}
</script>

<style>

</style>