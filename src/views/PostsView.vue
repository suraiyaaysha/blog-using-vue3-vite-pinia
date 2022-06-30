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
    <div class="posts-area my-5">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <h3 class="mb-4">All Posts</h3>
          </div>
          <p v-if="loading">Loading posts...</p>
          <p v-if="error">{{ error.message }}</p>
              <!-- <p v-if="posts" v-for="post in posts" :key="post.id"> -->

          <div class="col-lg-3" v-for="post in posts" :key="post.id">
            <div class="card post-item">
              <!-- <img src="..." class="card-img-top" alt="..."> -->
              <div class="card-body">
                <RouterLink :to="`/post/${post.id}`" class="card-title h5">{{ post.title.slice(0, 20) }}...</RouterLink>
                <p class="card-text">{{ post.body.slice(0, 60) }}...</p>
                <RouterLink :to="`/post/${post.id}`" class="btn btn-primary">See Details</RouterLink>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
