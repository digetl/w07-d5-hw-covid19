<template>
  <div id="app">
    <h1>Covid19 Tracker</h1>
  </div>
</template>

<script>
import World from './components/World.vue'

export default {
  name: 'App',
  data(){
    return{
      worlddata:{}
    }
  },
  methods: {

  },

  mounted(){
    fetch("https://api.covid19api.com/summary")
    .then(res => res.json())
    .then(data => this.worlddata = data)
    .catch(error => console.log("error:", error))
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
