<template lang="html">
<section>

  <h3 >Matches</h3>

<div v-for="match in matches" >

  <p>{{ match.homeTeam.name }} vs {{ match.awayTeam.name }}</p>

</div>

</section>

</template>

<script>
export default {
  name: 'matches',
  props: ['matches']
}
</script>

<style lang="css" scoped>

</style>
