<script setup>
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue'

components: {
  Header
}
</script>

<template>

  <Header />

  <RouterView />

</template>

<style>
@import '@/assets/css/base.css';
@import '@/assets/css/style.css';
</style>
