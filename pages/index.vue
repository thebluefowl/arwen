<template>
  <div>
    <Header />
    <ArticleList class="mt-8" :articles="articles" />
    </div>
</template>

<script>
import ArticleList from '~/components/ArticleList.vue'
import Header from '~/components/Header.vue'
export default {
  components: [Header, ArticleList],
  async asyncData ({ $content, params }) {
    const articles = await $content('articles')
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt', 'asc')
      .fetch()
    return {
      articles
    }
  }
}

</script>
