<template lang="html">
<!-- Put in this v-if so it would not try to access <thead>
  name unless there was data in it
 -->
  <section v-if="team">
    <li v-on:click="handleClick">{{ team.name }}</li>
  </section>
</template>

<script>

import { eventBus } from '../main.js';

export default {
  name: 'teams-list-item',
  props: ['team'],
  methods: {
    handleClick() {
    eventBus.$emit('team-selected', this.team)
    }
  }
}

</script>

<style lang="css" scoped>

li:hover {
  text-decoration: underline;
}

</style>
