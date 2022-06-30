<script setup>
    defineProps(['comments'])
</script>

<template>
    <div>
        <div v-for="comment in comments" :key="comment.id" class="d-flex comment-item">
            <div class="flex-shrink-0">
                <div class="comment-user-avatar bg-gray"> 
                    <img src="" alt="">
                </div>
            </div>
            <div class="flex-grow-1 ms-3">
                <h5>{{ comment.name }}</h5>
                <p>{{ comment.body }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>