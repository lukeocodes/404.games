<template>
  <div class="container">
    <div>
      <h1 class="title">
        404.games
      </h1>
      <div class="videos">
        <Video
          v-for="(video, index) in videos"
          :key="index"
          :video="video"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Video from '~/components/Video'

export default {
  components: {
    Video
  },

  async asyncData ({ $content, app }) {
    const videos = await $content('videos')
      .sortBy('published_at', 'desc')
      .fetch()

    return {
      videos
    }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
