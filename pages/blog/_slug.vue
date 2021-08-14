<template>
  <div class="max-w-screen-2xl mx-auto">
    <Header :showPrimaryTitle="false"/>
    <div class="bg-blue">
      <h1 class="font-display text-4xl font-bold p-12 pb-1">{{ article.title }}</h1>
      <div class="px-12 pb-5">{{ formatDate(article.createdAt) }} </div>
      <nuxt-content :document="article" class="font-serif px-12 tracking-wide leading-relaxed" />
      
    </div>
  </div>
</template>

<script>

import Header from '~/components/Header.vue'

export default {
  components: {Header},
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
