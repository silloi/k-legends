<template>
  <div class="header">
    <div class="logo">
      <nuxt-link to="/">
        K Legends
      </nuxt-link>
    </div>
    <div class="nav">
      <ul>
        <li>
          <nuxt-link to="/artists">
            アーティスト
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="/labels">
            レーベル
          </nuxt-link>
        </li>
        <li>
          <a href="#">
            記事
          </a>
        </li>
        <li>
          <nuxt-link to="/about">
            このサイトについて
          </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  components: {}
})
</script>

<style scoped>
.header {
  margin: 0 auto;
  display: flex;
  align-items: center;
  height: 80px;
  background-color: #fefefe;
  border-bottom: 1px solid #ccc;
}

.logo {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: inline-block;
  font-weight: 300;
  font-size: 24px;
  letter-spacing: 1px;
  margin-left: 40px;
}

.nav {
  margin-left: 30px;
}

.nav ul li {
  display: inline-block;
  font-size: 12px;
  padding-right: 16px;
}

a {
  text-decoration: none;
  color: #000;
}
</style>
