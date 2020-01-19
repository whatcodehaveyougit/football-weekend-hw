<template lang="html">

<!-- Taken away the section tags as want it to be an ul => li -->
<!-- This is rendered inside teams-list-item -->
    <li v-on:click="handleClick">{{ team.name }}</li>

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
