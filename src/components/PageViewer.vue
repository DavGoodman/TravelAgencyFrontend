<template>
    <div class="container">
        <h1 class="page-title">{{page.pageTitle}}</h1>
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
import axios from 'axios';
import FilmCard from './FilmCard.vue';

export default {
    components: {
        FilmCard
    },
    props: ['page'],
    data(){
        return {
            posts: [],
            movieTitle: ''
        }
    },
    mounted(){
        axios.get('https://localhost:7216/api/movies/all')
        .then(response => {
            this.posts = response.data;
            
            console.log(response);
        })
    }    
}
</script>