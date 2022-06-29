<script setup>
import { RouterLink } from 'vue-router'
import { storeToRefs } from 'pinia'; 
import { usePostStore } from '../stores/post';

const { posts, loading, error } = storeToRefs(usePostStore())
const { fetchPosts } = usePostStore()

fetchPosts()

</script>

<template>
  <main>
    <div class="container">
      <div class="row">
        <p v-if="loading">Loading posts...</p>
        <p v-if="error">{{ error.message }}</p>
            <!-- <p v-if="posts" v-for="post in posts" :key="post.id"> -->
            <div class="col-md-6 post-item" v-for="post in posts" :key="post.id">
              <RouterLink :to="`/post/${post.id}`">{{ post.title }}</RouterLink>
              <p>{{ post.body }}</p>
            </div>
      </div>
    </div>
  </main>
</template>
