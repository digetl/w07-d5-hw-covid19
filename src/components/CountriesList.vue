<template lang="html">

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

export default {
  name: "countries-list",
  props: ['countriesData'],
 
  components: {
    "list-component": ListComponent   
  }

}
</script>

<style>

</style>