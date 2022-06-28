<script setup>
    defineProps(['comments'])
</script>

<template>
    <div>
        <div v-for="comment in comments" :key="comment.id">
            <h3>{{ comment.name }}</h3>
            <p>{{ comment.body }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>