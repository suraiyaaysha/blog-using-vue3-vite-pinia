<script setup>
import { RouterLink } from "vue-router";
import { storeToRefs } from "pinia";
import { useCommentStore } from '../stores/comment'
import Comment from "../components/Comment.vue"

defineProps([ 'post', 'author' ])

const { getPostComments } = storeToRefs(useCommentStore())
const { fetchComments } = useCommentStore()

fetchComments()

</script>

<template>
    <div>
        <div class="post-details-top-part">
            <h2>{{ post.title }}</h2>
            <p v-if="author">Written by: <RouterLink :to="`/author/${author.username}`" class="fw-semibold">{{ author.name }}</RouterLink> | <span>Comments: {{ getPostComments.length }}</span> </p>
            <p>{{ post.body }}</p>
        </div>
        <hr>
        <div class="post-comment-part">
            <h3>Comments:</h3>
            <comment :comments="getPostComments"></comment>
        </div>

    </div>
</template>

<style scoped>
.post-details-top-part {
    margin-bottom: 20px;
}
.post-comment-part {
    margin-top: 20px;
}
</style>