<template lang="html">
  <div>
       <GChart
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
  },
  props: ['globalData'],

  data(){
    objToArray:{}
    toGrapfData:[]

      return {

        chartData: [addedHeaders],
      
          chartOptions: {
              // width: 600,
              // height: 200,
              title: 'Todays data'
          }
      }
  },
  computed: {

    objToArray: function() {
     return Object.entries(this.globalData)
    },

    addedHeaders: function() {
      return objToArray.unshift(['Outcome', 'number'])
    }

  },
  
  components: {
    GChart
  }
}

</script>

<style>

</style>