<template>
  <div>
    <Header :showPrimaryTitle="true"/>
    <ArticleList :articles="articles.latest" />
    </div>
</template>

<script>
import ArticleList from '~/components/ArticleList.vue'
import Header from '~/components/Header.vue'
export default {
  components: {Header, ArticleList},
  async asyncData ({ $content, params }) {
    const latest = await $content('articles')
      .only(['title', 'summary', 'createdAt', 'slug', 'category'])
      .sortBy('createdAt', 'asc')
      .limit(4)
      .fetch()
    const archives = await $content('articles')
      .only(['title', 'summary', 'createdAt', 'slug', 'category'])
      .sortBy('createdAt', 'asc')
      .skip(4)
      .fetch()
    return {
      articles: {latest, archives}
    }
  }
}

</script>
