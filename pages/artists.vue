<template>
  <div class="container">
    <h1 class="title">アーティスト</h1>
    <ul>
      <li v-for="(artist, index) in artists" :key="index">
        <nuxt-link :to="`/artist/${artist.slug}`">{{ artist.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  components: {},
  async asyncData({ $content }) {
    const artists = await $content(`artist`).fetch()

    return { artists }
  }
})
</script>

<style scoped>
.container {
  margin: 0 auto;
  padding-top: 40px;
  /* min-height: 100vh; */
  /* display: flex; */
  justify-content: center;
  align-items: center;
  text-align: center;
  max-width: 786px;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 42px;
  color: #35495e;
  letter-spacing: 1px;
}

.description {
  font-weight: 300;
  font-size: 24px;
  color: #526488;
  word-spacing: 5px;
}

li {
  padding-bottom: 8px;
}
</style>
