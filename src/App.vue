<script setup>
import { ref } from 'vue'
import BlogPost from './components/BlogPost.vue';
import PaginatePost from './components/PaginatePost.vue';
import SpinnerLoad from './components/SpinnerLoad.vue';

const posts = ref([])
const favorito = ref("")
const Cambiar = (post) => {
  favorito.value = post
}
const postXpage = 20;
const inicio = ref(0)
const fin = ref(postXpage)
const lodin = ref(true);
const next = () => {
  inicio.value = inicio.value + postXpage;
  fin.value = fin.value + postXpage;
}
const previus = () => {
  inicio.value = inicio.value - postXpage;
  fin.value = fin.value - postXpage;
}

fetch("https://jsonplaceholder.typicode.com/posts")
  .then(res => res.json())
  .then((data) => {
    posts.value = data;
  })
  .finally(() => lodin.value = false)


</script>


<template>
  <SpinnerLoad v-if="lodin"></SpinnerLoad>
  <div class="container-main" v-else>
    <h1>Mi post favorito: {{ favorito }}</h1>

    <PaginatePost @next="next" @previus="previus" :inicio="inicio" :posts="posts" :postXpage="postXpage"></PaginatePost>

    <div class="container">
      <BlogPost v-for="post in posts.slice(inicio, fin)" :key="post.id" :title="post.title" :id="post.id"
        :body="post.body" @Cambiar="Cambiar" />

    </div>

  </div>

</template>

<style>
body {
  min-height: 100vh;
}
.container-main, #app, body {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.container {
  width: 90%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 1rem;
}
</style>