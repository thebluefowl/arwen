<template>
  <div class="px-4">
    <ol>
      <li v-for="article of articles" :key="article.slug">
        {{ article.title }}
      </li>
    </ol>
  </div>
</template>
<script>
export default {
  props: {
    articles: Object
  }
}
</script>
