<script setup>
  import { RouterLink } from 'vue-router';
  import { storeToRefs } from 'pinia';
  import { useAuthorStore } from '../stores/author';

  const { authors } = storeToRefs(useAuthorStore())
  const { fetchAuthors } = useAuthorStore()

  fetchAuthors()

</script>

<template>
  <div class="author-page my-5">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h3 class="mb-4">All Author</h3>
        </div>
        <!-- <p v-if="authors" v-for="author in authors" :key="author.id"> -->
          
        <div class="col-lg-6" v-for="author in authors" :key="author.id">
          <div class="card author-item">
            <div class="card-body">
              <h5 class="card-title">{{ author.name }}</h5>
              <p class="mb-2 text-muted">Email: {{author.email}}</p>
              <p class="text-muted"> <span class="">Address:</span> {{author.address.suite}},{{author.address.street}},{{author.address.street}}</p>
              <RouterLink :to="`/author/${author.username}`" class="btn btn-primary">Author Details</RouterLink>
            </div>
          </div>
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
