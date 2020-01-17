<template lang="html">
  <section>
    <ul v-for="team in teams">

       <li>{{ team.name }}</li>
    </ul>
    <p>From teams list</p>
  </section>
</template>

<script>
// import  TeamsListItem from './TeamsListItem.vue';

export default {
  name: 'teams-list',
  props: ['teams'],
  // components: {
  //   "teams-list-item": TeamsListItem
  // }
}
</script>

<style lang="css" scoped>
</style>
