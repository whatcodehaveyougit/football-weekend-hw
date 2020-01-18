<template lang="html">
  <section>
    <ul >
       <teams-list-item v-for="(team, index) in teams" :team="team" :key="index">
       </teams-list-item>

    </ul>
    <p>From teams list</p>
  </section>
</template>

<script>
import  TeamsListItem from './TeamsListItem.vue';

// Being exported to the top of the page
export default {
  name: 'teams-list',
  // Props being handed to this file directly from data in App.vue
  props: ['teams'],

  // components being handed from the import
  components: {
    "teams-list-item": TeamsListItem
  }
}
</script>

<style lang="css" scoped>
li {
  list-style: none;
}
</style>
