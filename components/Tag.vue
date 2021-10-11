<template>
    <NuxtLink :to="categoryUrl">
        <span class="uppercase font-bold text-xs">
            {{ category }} 
        </span>
    </NuxtLink>
</template>

<script>
export default {
    name: 'Tag',
    props: ["category"],
    computed: {
        categoryUrl: function() {
            return "/category/" + this.category
        }
    }
}
</script>