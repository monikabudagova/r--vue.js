<template>
    <div class="post">
        <img src="https://blog.mann-ivanov-ferber.ru/wp-content/uploads/2017/11/untit.jpg">
        <h1>{{ post.title }}</h1>
        <p>{{ post.body }}</p>
    </div>
</template>

<style scoped>
 .post {
    background-color: brown;
    color: wheat;
    padding: 10px 0;
 }

 img {
    width: 100%;
    height: 300px;
    object-fit: cover;
 }
</style>

<script setup>
    import { useRoute } from 'vue-router'
    import { ref } from 'vue'
    const route = useRoute()
    const id = parseInt(route.params.id)

    fetch(`https://dummyjson.com/post/`+id)
    .then(res => res.json())
    .then(res => post.value = res)
    
   
    
    // const post = posts.find(id)
    const post = ref()
</script>