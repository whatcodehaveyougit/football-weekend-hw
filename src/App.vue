<template>
  <div id="app">
    <h1 class="">From App</h1>
      <div class="content-container">
        <teams-list :teams="teams"></teams-list>
        <team-details class="team-details" :team="selectedTeam">
        </team-details>
        <!-- This :team is NOT a banana -->
      </div>
  </div>
</template>

<script>

import TeamsList from './components/TeamsList.vue';
import TeamsListItem from './components/TeamsListItem.vue';
import TeamDetails from './components/TeamDetails.vue';
import { eventBus } from './main.js';

export default {
  name: 'app',
  data() {
    // Must Return the data
    return {
      teams: [],
      selectedTeam: null
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

    eventBus.$on('team-selected', (team) => {
      this.selectedTeam = team
    })
  },
  // These are the components which will help us construct the output at the top
  components: {
    "teams-list": TeamsList,
    "teams-list-item": TeamsListItem,
    "team-details": TeamDetails
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}

.content-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

h1 {
  text-align: center;
}
</style>
