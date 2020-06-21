<template>
  <div class="container">
    <h1 class="title">{{ page.title }}</h1>
    <p class="description">{{ page.description }}</p>
    <div class="genres">
      <span
        v-if="page.genres.filter((genre) => genre === 'hiphop').length"
        class="genres--tab"
        >#hiphop</span
      >
      <span
        v-if="page.genres.filter((genre) => genre === 'rnb').length"
        class="genres--tab"
        >#rnb</span
      >
      <span
        v-if="page.genres.filter((genre) => genre === 'ballad').length"
        class="genres--tab"
        >#ballad</span
      >
    </div>
    <nuxt-content :document="page"></nuxt-content>
    <h2>関連するアーティスト</h2>
    <ul>
      <li v-for="(artist, index) in page.related" :key="index">
        <nuxt-link :to="`/artist/${artist}`">
          {{ artist }}
        </nuxt-link>
      </li>
    </ul>
    <h2>{{ page.title }}に関する記事</h2>
    <h2>Wikipedia</h2>
    <a
      :href="`https://en.wikipedia.org/wiki/${page.wikipedia || page.title}`"
      target="_blank"
      rel="noopener noreferrer"
      >Wikipedia</a
    >
    <h2>YouTube</h2>
    <a
      :href="`https://www.youtube.com/results?search_query=${page.title}`"
      target="_blank"
      rel="noopener noreferrer"
      >YouTubeで検索</a
    >
    <Culator></Culator>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Culator from '@/components/Culator.vue'

export default Vue.extend({
  components: {
    Culator
  },
  async asyncData({ $content, params }) {
    const page = await $content(`artist/${params.artist}`).fetch()

    return { page }
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
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.description {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
}

h2 {
  margin: 0;
  font-size: 24px;
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
</style>
