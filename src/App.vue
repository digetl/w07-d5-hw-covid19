<template>
  <div id="app">
    <h1>Covid19 Tracker</h1>
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
      </div>

      <div class="col-1"
        <countries-list v-bind:countriesData="countriesData"></countries-list>
      </div>

  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import CountryDetail from './components/CountryDetail.vue'

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
    "country-detail": CountryDetail
  }
}
</script>

<style>
#app {
  padding:0 5%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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

</style>
