<template>
  <div>
    {{ video.title }}
  </div>
</template>

<script>
export default {
  props: {
    video: {
      type: Object,
      required: true
    }
  },

  computed: {
    language () {
      return this.$i18n.locales.filter(l => l.code === this.post.locale)[0]
    }
  }
}
</script>
