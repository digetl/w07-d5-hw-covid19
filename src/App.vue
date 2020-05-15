<template>
  <div id="app">
    <h1>Covid19 Tracker</h1>
    <world-component></world-component>
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
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
