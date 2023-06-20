<template>
    <div class="container">
        <h1 class="page-title">FilmVuer</h1>
        <div class="posts-container">
            <FilmCard
            v-for="(post, index) in posts"
            :key="index"
            :post="post">

            </FilmCard>
        </div>
        
    </div>
</template>

<script>

import FilmCard from './FilmCard.vue';

export default {
    components: {
        FilmCard
    },
    props: ['page', 'posts'],
}
</script>