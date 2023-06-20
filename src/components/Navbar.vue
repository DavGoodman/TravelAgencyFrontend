<template>
    <nav 
                class="navbar navbar-expand-lg"
                :class="[`navbar-${theme}`, `bg-${theme}`]"
            >
                <div class="container-fluid">
                    <a class="navbar-brand" href="#">FilmVuer</a>
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">

                    <li class="nav-item" :key="index">
                        
                        <div class="dropdown">
                            <button class="dropbtn">Genres</button>
                            <div class="dropdown-content">
                                <a h
                                ref="#" 
                                v-for="(genre, index) in genres"
                                :key="index"
                                @:click.prevent="sortByGenre(genre.id)"
                                >
                                {{ genre.name }}
                                </a>
                            </div>
                        </div>

                    </li>

                </ul>
                
                <button
                    class="btn btn-primary"
                    @click.prevent="changeTheme()"
                    >
                    Toggle Navbar
                </button>
                
                </div>
            </nav>
</template>

<script>


export default {
    props: ['navLinkClick', 'genres', 'sortByGenre'],
    data() {
        return {
            theme: 'light',
        };
    },
    methods: 
    {
        changeTheme() {
            this.theme = this.theme == 'light' ? 'dark' : 'light';
        },
    }
        }
</script>

