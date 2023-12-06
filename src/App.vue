<template>
    <navbar 
        :nav-link-click="(index) => activePage = index" 
        :changeVat="changeVat"
        :setPosts = "setPosts"
    >
    </navbar>


    <page-viewer 

        :posts="posts"
        :vat="vat"
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
        PageViewer,
    },
    data() 
    {
        return {
            posts : [],
            vat : false
        }

    },
    methods:{
        changeVat(bool){
            console.log("vat cicked", bool);
            this.vat = bool;
        },

        async setPosts(link){
            console.log(link);
            await axios.get(link)
                .then(response => {
                this.posts = response.data;
                })
            console.log(this.posts);
        }
    }
    
    
}
</script>