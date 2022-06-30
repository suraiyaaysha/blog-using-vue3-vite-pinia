<script setup>
import { RouterLink } from 'vue-router';

defineProps(['author', 'posts'])
</script>

<template>
    <div class="single-author">
        <h1>{{ author.name }}</h1>
        <p>Total {{posts.length}} posts written by <span class="fw-semibold">{{ author.name }}</span>.</p>

        <div class="all-posts-of-a-author mt-4 mb-3">
            <h5>All Posts from {{ author.name }}</h5>
        </div>
        <div class="" v-for="post in posts" :key="post.id">
            <div class="card post-item">
              <div class="card-body">
                <h5><RouterLink :to="`/post/${post.id}`" class="card-title">{{ post.title }}</RouterLink></h5>
                <!-- <RouterLink :to="`/post/${post.id}`" class="btn btn-primary">See Details</RouterLink> -->
              </div>
            </div>
          </div>
    </div>
</template>