<template>
  <article class="max-w-screen-sm bg-gray-50 mx-auto p-6">
    <h1 class="text-center">{{ article.title }}</h1>
    <nuxt-content :document="article" />
    <div>Data: {{ formatDate(article.createdAt) }} </div>
  </article>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const article = await $content('articles', params.slug).fetch()

    return { article }
  },
  methods: {
    formatDate (date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
  }
}
</script>
<style scoped>
</style>
