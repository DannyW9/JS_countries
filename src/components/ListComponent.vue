<template lang="html">

  <option @click="handleClick">{{country.name}}</option>

</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: 'list-component',
  props: ['country'],
  methods: {
    handleClick: function(){
      eventBus.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
