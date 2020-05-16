<template lang="html">
        <li>{{country.Country}}</li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['country'],
  methods: {

  }
}
</script>

<style>

</style>
