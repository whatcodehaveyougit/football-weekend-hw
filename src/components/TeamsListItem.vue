<template lang="html">
  <section>
    <li>{{ team.name }}</li>
    <p>From Teams List Item</p>
  </section>
</template>

<script>

// Give the top of the file stuff
export default {
  name: 'team-list-item',
  // Data - Props is a single beer
  props: ['team']
}
</script>

<style lang="css" scoped>

li:hover {
  text-decoration: underline;
}

</style>
