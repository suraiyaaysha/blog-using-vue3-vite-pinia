<script setup>
  import { computed } from 'vue'
  import { useRoute } from 'vue-router';
  import { storeToRefs } from 'pinia';
  import { useAuthorStore } from '../stores/author';
  import { usePostStore } from '../stores/post';
  import Author from '../components/Author.vue'

  const route = useRoute()
  const { authors } = storeToRefs(useAuthorStore())
  const { getPostsPerAuthor } = storeToRefs(usePostStore())
  const { fetchPosts } = usePostStore()

  const getAuthorByUserName = computed(() => {
    return authors.value.find( (author) => author.username === route.params.username )
  })

  fetchPosts()

</script>

<template>
<div class="author-details my-5">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <author
          :author="getAuthorByUserName"
          :posts="getPostsPerAuthor(getAuthorByUserName.id)">
          </author>
        </div>
      </div>
    </div>
</div>
</template>

<style>
/* @media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
} */
</style>
