<template lang="html">
  <div v-if="team" class="team-details">
    <h3>{{ team.name }}</h3>
    <dl>
      <dt>Website: {{ team.website }} </dt>
      <dt>Phone: {{ team.phone }}% </dt>
      <p>test</p>
    </dl>
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'team-details',
  props: ['team'],
}
</script>

<style lang="css" scoped>
.team-details {
  text-align: center;
}
</style>
