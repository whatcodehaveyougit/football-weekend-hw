<template lang="html">
  <section>
    <ul >
       <teams-list-item v-for="(team, index) in teams" :team="team" :key="index">
         <!-- Team List Item goes in there
       Being Handed to Us on import
     Being Registered in Components -->
       </teams-list-item>

    </ul>
    <p>From teams list</p>
  </section>
</template>

<script>
// Import this item to display inside the components tags
import  TeamsListItem from './TeamsListItem.vue';

// Export this info to the top of this page so it can render
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
