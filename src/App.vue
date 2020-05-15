<template>
  <div id="app">
    <h1>Covid19 Tracker</h1>
    <world-component></world-component>
    <div class="container">
      <h1>World data</h1>
        <ul>
          <li>New Confirmed Cases: {{globalData.NewConfirmed}}</li>
          <li>New Deaths: {{globalData.NewDeaths}}</li>
          <li>New Recovered: {{globalData.NewRecovered}}</li>
          <li>Total Confirmed Cases: {{globalData.TotalConfirmed}}</li>
          <li>Total Deaths: {{globalData.TotalDeaths}}</li>
          <li>Total Recovered: {{globalData.TotalRecovered}}</li>

        </ul>
    </div>
  </div>
</template>

<script>
import WorldComponent from './components/World.vue'
import {eventBus} from "@/main.js"

export default {
  name: 'App',
  data(){
    return{
      worlddata:{}
    }
  },
  methods: {

  },
  computed: {
    globalData: function(){
      return this.worlddata['Global'];
    }
  },

  mounted(){
    fetch("https://api.covid19api.com/summary")
    .then(res => res.json())
    .then(data => this.worlddata = data)
    .catch(error => console.log("error:", error))
  },
  components: {
    "world-component": WorldComponent
  }
}
</script>

<style>
#app {
  padding:0 20%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container{
  padding: auto;
}

ul {
  list-style: none;
  padding-inline-start: 0px;
  line-height: 2rem;

}

</style>
