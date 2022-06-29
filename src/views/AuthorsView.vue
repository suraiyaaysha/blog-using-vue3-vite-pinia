<script setup>
  import { RouterLink } from 'vue-router';
  import { storeToRefs } from 'pinia';
  import { useAuthorStore } from '../stores/author';

  const { authors } = storeToRefs(useAuthorStore())
  const { fetchAuthors } = useAuthorStore()

  fetchAuthors()

</script>

<template>
  <div class="author-page">
    <div class="container">
      <div class="row">
        <div class="col-12">
              <ul>
                <!-- <p v-if="authors" v-for="author in authors" :key="author.id"> -->
                <li v-for="author in authors" :key="author.id">
                  <RouterLink :to="`/author/${author.username}`">{{ author.name }}</RouterLink>
                </li>
            </ul>
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
