<template lang="html">
<ul>
<country-list-item v-for="(country, index) in countries" :country="country" :key="index" />
</ul>

</template>

<script>
import CountryItem from './countryItem.vue'
export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "country-list-item": CountryItem
  }
}
</script>

<style lang="css" scoped>
</style>
