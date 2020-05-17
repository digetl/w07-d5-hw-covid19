<template lang="html">
  <div>
       <GChart
        v-if="chartData"
        type="ColumnChart"
        :data="chartData"
        :options="chartOptions"
        />


  </div>
  
</template>

<script>
import { GChart } from 'vue-google-charts'
 
export default {
  name: 'global-covid-chart',
  components: {
    GChart
  }
}

</script>

<style>

</style>