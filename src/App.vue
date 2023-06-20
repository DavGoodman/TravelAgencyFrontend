<template>
    <navbar 
        :nav-link-click="(index) => activePage = index" 
        :genres="genres"
        :sort-by-genre="sortByGenre"
    >
    </navbar>

    <page-viewer 
        :posts="posts"
        >
    </page-viewer>

</template>

<script>
import PageViewer from './components/PageViewer.vue';
import Navbar from './components/Navbar.vue';
import axios from 'axios';

export default {
    components: {
        Navbar,
        PageViewer
    },
    data() 
    {
        return {
            posts : [],
            genres : []
        }

    },
    mounted(){
        axios.get('https://localhost:7216/api/movies/all')
            .then(response => {
                this.posts = response.data;

        }),
        axios.get('https://localhost:7216/api/genres/all')
                .then(response => {
                    this.genres = response.data;

        })

    },
    methods:{
        sortByGenre(genreId){
            console.log(genreId);

            var rawGenres = JSON.parse(JSON.stringify(this.genres));

            var newPosts = rawGenres
                            .filter(genre => genre.id == genreId)
                                .map(genre => genre.movies)[0];

            this.posts = newPosts;
        }
    }
    
    
}
</script>