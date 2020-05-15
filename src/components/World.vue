<template>
<div>

<h1>World data</h1>
  <ul>
    <li>
     Text: {{globalData.NewConfirmed}} 
    </li>
  </ul>
</div>
  
</template>

<script>
import { eventBus } from '../main.js'


export default {
  name: "world-component",
  props: {
    // NewConfirmed: Number,
    // NewDeaths: Number,
    // NewRecovered: Number,
    // TotalConfirmed: Number,
    // TotalDeaths: Number,
    // TotalRecoverd: Number
    
  },
  methods: {
    
  }

}
</script>

<style>

</style>