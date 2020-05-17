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
  props: ['globalData'],

  data(){
      return {
          chartOptions: {
              width: 600,
              height: 200,
              title: 'Current data',
              colors: ['#084887', '#f58a07', '#f9ab55', '#f7f5fb', '#909cc2', '#C1BB8F', '#A176BC']
          }
      }
  },
  components: {
    GChart
  }
}

</script>

<style>

</style>