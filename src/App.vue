<template lang="html">
  <div>
    <h1>Countries</h1>
    <div class="list">
      <countries-list :countries='countries'></countries-list>
      <country-detail :country='selectedCountry'></country-detail>
    </div>

  </div>
</template>

<script>
import CountryList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import {eventBus} from './main.js';
export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    "countries-list": CountryList,
    "country-detail": CountryDetail
  }
}
</script>

<style lang="css" scoped>
.list {
  display: flex;
  justify-content: space-between;
}
</style>
