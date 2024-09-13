<template>
    <ul>
        <CardPostView />
    </ul>
</template>

<style scoped>
    ul {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 20px;
    }
</style>

<script setup>
    import { onMounted } from 'vue';
    import CardPostView from './CardPostView.vue';


    onMounted(() => {
        // console.log(posts);
    })
</script>