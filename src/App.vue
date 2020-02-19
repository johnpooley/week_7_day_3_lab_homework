<template lang="html">
  <div class="mainPage">
<h1>List Of Countries</h1>
<country-detail v-bind:country="selectedCountry"/>

<countries-list v-bind:countries="countries"></countries-list>
  </div>

</template>

<script>

import listOfCountries from './components/listOfCountries.vue';
import countryDetail from './components/countryDetail.vue';
import {eventBus} from './main.js'


export default {
  name: 'app',
  data(){
    return{
    countries:{},
    selectedCountry: null
}
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(result => result.json())
    .then(countries => this.countries = countries),

    eventBus.$on('country-selected', (country) => this.selectedCountry = country)
  },
  components: {
    "countries-list":listOfCountries,
    "countryDetail":countryDetail
  }

}
</script>

<style lang="css" scoped>
</style>
