<template>
  <div class="max-w-screen-2xl mx-auto">
    <Header />
    <article class="bg-gray-50 p-6">
      <h1 class="text-center font-display text-2xl">{{ article.title }}</h1>
      <nuxt-content :document="article" class="font-serif" />
      <div>Data: {{ formatDate(article.createdAt) }} </div>
    </article>
  </div>
</template>

<script>

import Header from '~/components/Header.vue'

export default {
  components: [Header],
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
