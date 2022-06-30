<script setup>
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'

components: {
  Header
}
</script>

<template>

  <Header />

  <RouterView />

  <Footer />

</template>

<style>
@import '@/assets/css/base.css';
@import '@/assets/css/style.css';
</style>
