<template lang="html">
  <div v-if="country">
    <h3>{{country.name}}</h3>
    <p>Population: {{country.population}}</p>
    <p>Capital: {{country.capital}}</p>
    <img :src="country.flag">
    <ul>
      <li v-for="language in country.languages">{{language.name}}</li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
img {
  width: 150px;
  height: 100px;
}

</style>
