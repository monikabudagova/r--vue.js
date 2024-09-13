<template>
    <li class="post" v-for="(post, index) in posts" :key="post.id">
        <h3>{{ post.title }}</h3>
        <img src="https://blog.mann-ivanov-ferber.ru/wp-content/uploads/2017/11/untit.jpg" alt="Нет обложки">
        <ul class="tags">
            <li class="tag" v-for="tag in post.tags" :key="tag.id">
                {{ tag }}
            </li>
        </ul>
        <RouterLink :to="'/post/' + (index + 1)">Читать подробнее</RouterLink>
    </li>
</template>

<script setup>
    import { ref } from 'vue'

    const posts = ref([])

    fetch('https://dummyjson.com/posts/')
    .then(res => res.json())
    .then(res => posts.value = res.posts)
</script>


<style scoped>
    .post:hover {
        transition: all .1s linear;
        -webkit-box-shadow: 5px 5px 5px -5px rgba(34, 60, 80, 0.6);
        -moz-box-shadow: 5px 5px 5px -5px rgba(34, 60, 80, 0.6);
        box-shadow: 5px 5px 5px -5px rgba(34, 60, 80, 0.6);
        border-color:#000000;
    }

    .post {
        border: 2px solid #00000000;
        background-color: wheat;
        color: brown;
        padding: 10px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 10px;
    }

    h3 {
        height: 50px;
    }

    .tags {
        display: flex;
        gap: 10px;
    } 

    a {
        padding: 10px;
        background-color: brown;
        text-decoration: none;
        color: wheat;
    }

    a:hover {
        filter: brightness(1.2);
    }
</style>