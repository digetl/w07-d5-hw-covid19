<template lang="html">

<div>

  <div class="container">
    <h1 id="cl-headher">Countries list</h1>
      <ul class="countries-list">
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
#cl-headher{
  padding-right: 5%;
}
.countries-list{
  padding: 0 10%;
  height:60vh;
  width:75%;
}
ul{
  overflow: auto;
}

::-webkit-scrollbar {
  -webkit-appearance: none;
  width: 10px;
}

::-webkit-scrollbar-thumb {
  border-radius: 5px;
  background-color: rgba(0,0,0,.5);
  -webkit-box-shadow: 0 0 1px rgba(255,255,255,.5);
}
</style>