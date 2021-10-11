<template>
  <div class="px-6">
    <div class="grid grid-cols-1 md:grid-cols-2">
      <div v-for="article in articles" :key="article.title">
        <Card v-bind:article = article />
      </div>
    </div>
  </div>
</template>
<script>

import Card from "./Card.vue"
export default {
  name: 'ArticleList',
  components:{Card},
  props: {
    articles: Array,

  }
}
</script>
