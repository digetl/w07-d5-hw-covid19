<template>

<div>

  <div class="container">
    <h1>Countries list</h1>
      <ul>
        <list-component v-for="(country, index) in countriesData" :country="country" :key="index"></list-component>
      </ul>
  </div>

</div>
  
</template>

<script>
import ListComponent from './ListComponent.vue'
import { eventBus } from '../main.js'

export default {
  props: ['countriesData'],
  name: "countries-list",

  components: {
    "list-component": ListComponent   
  }

}
</script>

<style>

</style>