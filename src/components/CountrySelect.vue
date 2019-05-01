<template lang="html">

  <div>
    <select @change="handleChange" v-model="chosenCountry">
      <option v-for="(country, index) in countries" :country="country" :key="index" :value="country">{{ country.name }}</option>
    </select>

  </div>

</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: 'countries-select',
  data(){
    return {
      chosenCountry: null
    }
  },
  props: ['countries'],
  methods: {
    handleChange(){
      eventBus.$emit('country-selected', this.chosenCountry)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
