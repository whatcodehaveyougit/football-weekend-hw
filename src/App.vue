<template>
  <div id="app">
    <p class="">From App</p>
    <teams-list :teams="teams"></teams-list>
  </div>
</template>

<script>

import TeamsList from './components/TeamsList.vue'
// import TeamsListItem from './components/TeamsListItem.vue'

export default {
  name: 'app',
  data() {
    // Need to return Data
    return {
      teams: []
    }
  },
  mounted() {
    fetch('http://api.football-data.org/v2/competitions/2000/teams', {
    headers: {
      // Causse of dashes it wants quotes
      "X-Auth-Token": "f9ca195aca3c4f19935355ac2e0f1f02"
    }
  })
    .then(response => response.json())
    .then(teams => this.teams = teams.teams)
  },
  components: {
    "teams-list": TeamsList,
    // "teams-list-item": TeamsListItem
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
}
</style>
