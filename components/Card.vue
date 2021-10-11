<template>
    <div class="p-6">
        <h2 class="text-3xl font-bold my-1 ">
            <NuxtLink :to="linkToBlog">{{article.title}}</NuxtLink>
        </h2>
        <p class="font-serif tracking-wide leading-relaxed line-clamp-5">{{ article.summary }}</p>
        <div class="flex items-center justify-between my-3">
            <!-- <div>Vishnu Jayadevan</div> -->
            <Tag :category="article.category"/>
            <span class="uppercase font-bold text-xs"> {{ formatDate(article.createdAt) }}</span>
        </div>

    </div>
</template>

<script>
import Tag from './Tag.vue'
export default {
    name: 'Card',
    components: {Tag},
    props: ['article'],
    methods: {
        formatDate (date) {
        const options = { year: 'numeric', month: 'long', day: 'numeric' }
        return new Date(date).toLocaleDateString('en', options)
    }},
    computed: {
        linkToBlog: function() {
            return "/blog/"+this.article.slug
        }
    }
}
</script>