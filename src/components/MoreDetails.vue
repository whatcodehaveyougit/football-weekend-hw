<template lang="html">
  <div id="example-1">
  <button v-on:click="counter += 1">Add 1</button>
  <p>The button above has been clicked {{ counter }} times.</p>

<!-- Looping the data in this file instead of creating new component -->
  <div v-for="post in posts">
    {{ post.title }}
  </div>

</div>

</template>

<script>


export default {
  name: 'more-details',
  // Seems like we always need the [] brackets here
  // props: ['counter'],
  data() {
    return {
      //
      counter: 1,
      // Passing Data up to be looped
      posts: [
     { id: 1, title: 'My journey with Vue' },
     { id: 2, title: 'Blogging with Vue' },
     { id: 3, title: 'Why Vue is so fun' }
   ]
    }
  },
  // components: {
  //   "blog-post": BlogPost
  // }
}
</script>

<style lang="css" scoped>
</style>
