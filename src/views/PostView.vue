<script setup>
import { useRoute } from 'vue-router'
import { storeToRefs } from 'pinia'
import { useAuthorStore } from '../stores/author'
import { usePostStore } from '../stores/post'
import Post from '../components/Post.vue'

const route = useRoute()
const { getPostAuthor } = storeToRefs(useAuthorStore())
const { fetchAuthors } = useAuthorStore()
const { post, loading, error } = storeToRefs(usePostStore())
const { fetchPost } = usePostStore()


fetchAuthors()
fetchPost(route.params.id)

</script>

<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <p v-if="loading">Loading...</p>
                    <p v-if="error">{{ error.message }}</p>
                    <div v-if="post">
                        <post :post="post" :author="getPostAuthor"></post>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>