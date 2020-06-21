<template>
  <div class="container">
    <h1 class="title">レーベル</h1>
    <ul>
      <li v-for="(label, index) in labels" :key="index">
        <nuxt-link :to="`/labels/${label.slug}`">{{ label.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  components: {},
  async asyncData({ $content }) {
    const labels = await $content(`labels`).fetch()

    return { labels }
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

h2 {
  margin: 0;
  font-size: 20px;
  padding-top: 36px;
}

.links {
  padding-top: 15px;
}

.genres {
  padding-top: 20px;
}

.genres--tab {
  font-size: 1.4em;
  border: 2px solid #cccc00;
  border-radius: 4px;
  padding: 4px;
}

li {
  padding-bottom: 8px;
}
</style>
