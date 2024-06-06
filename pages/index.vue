<template>
    <ul>
        <li v-for="catgeory in triviaCategories" :key="catgeory.id">
            {{ catgeory.name }}
        </li>
    </ul>
</template>

<script setup lang="ts">
const triviaCategories = ref([])
const { data: categories } = useFetch('https://opentdb.com/api_category.php')
triviaCategories.value = categories?.value?.trivia_categories || []
</script>