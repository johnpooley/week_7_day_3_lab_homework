<template lang="html">
  <div v-if="country" class="selected-country">

<h3>Welcome to {{this.country.name}}</h3>
<p>Capital is {{this.country.capital}}</p>
<p>Population is {{this.country.population}}</p>
<img v-bind:src="country.flag" :alt="country.name" width=250>

</div>
</template>

<script>
export default {
  name: "country-detail",
  props:['country']
}
</script>

<style lang="css" scoped>
</style>
