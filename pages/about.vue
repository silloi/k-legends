<template>
  <div class="container">
    <h1>About</h1>
    <h2>このサイトについて</h2>
    <p>
      K
      Legendsは、主に韓国のラッパー・ヒップホップアーティストについて、日本語の情報を集積・提供するために設置されました。
    </p>
    <h2>作者について</h2>
    <img
      :src="require('~/assets/images/icon_sil5.png')"
      width="200px"
      height="200px"
    />
    <p>
      Sil5は、神戸市出身のDJ、トラックメイカー、Webエンジニア。京都・木屋町で音楽活動をスタートし、現在は東京の自宅シェアハウスを中心に活動している。韓国のヒップホップやクラブシーンに精通しており、ボーカロイドをはじめとする日本のポップサウンドとの融合を試みている。
    </p>
    <p>
      <a href="https://www.youtube.com/channel/UCRKe0-ZLywAFvEieOF38psQ"
        >YouTube</a
      >
    </p>
    <p>
      <a href="https://soundcloud.com/silloi">SoundCloud</a>
    </p>
    <p>
      <a href="https://mixcloud.com/silloi/">Mixcloud</a>
    </p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  components: {},
  async asyncData({ $content }) {
    const page = await $content(`about`).fetch()

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
</style>
