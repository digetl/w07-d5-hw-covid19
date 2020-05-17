<template>
  <div id="app">
    <h1 class="app-title">Covid19 Tracker</h1>
    <div class="grid-container">
      <div class="col-1">
        <h2>World data as of {{prettyDateOfData}}</h2>
        <ul>
          <li>New Confirmed Cases: {{globalData.NewConfirmed.toLocaleString()}}</li>
          <li>New Deaths: {{globalData.NewDeaths.toLocaleString()}}</li>
          <li>New Recovered: {{globalData.NewRecovered.toLocaleString()}}</li>
          <li>Total Confirmed Cases: <strong>{{globalData.TotalConfirmed.toLocaleString()}}</strong></li>
          <li>Total Deaths: {{globalData.TotalDeaths.toLocaleString()}}</li>
          <li>Total Recovered: <strong>{{globalData.TotalRecovered.toLocaleString()}}</strong></li>
        </ul>

        <h2>Chart Data</h2>
        <chart-component>v-bind:globalData="globalData"</chart-component>


      </div>

      <div class="col-1">
        <countries-list v-bind:countriesData="countriesData"></countries-list>
      </div>
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import CountryDetail from './components/CountryDetail.vue'

import ChartComponent from './components/ChartComponent.vue'

import {eventBus} from "@/main.js"

export default {
  name: 'App',
  data(){
    return{
      worlddata:{},
      errorMessage:""
    }
  },
 

  methods: {
   
  },
  computed: {
    globalData: function(){
      return this.worlddata['Global'];
    },
    countriesData: function() {
      return this.worlddata['Countries'];
    },
  
    prettyDateOfData: function() {
      return new Date(this.worlddata['Date']);
    },

    showdetails: function() {
      return false;
    }
   

  },

  mounted(){
    fetch("https://api.covid19api.com/summary")
    .then(res => res.json())
    .then(data => this.worlddata = data)
    .catch(error => this.errorMessage = error)
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail,
    "chart-component": ChartComponent
  }
}
</script>

<style>
#app {
  padding:0%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
}

body{
background-image: url('assets/virus-light2.jpg');
background-repeat: no-repeat;
background-size: cover;

}

.grid-container{
  display: grid;
  grid-template-columns: 50% 50%;

}

ul {
  list-style: none;
  padding-inline-start: 0px;
  line-height: 2rem;

}

.app-title{
  font-size: 3rem;
  padding-top: 2rem;
}

</style>
