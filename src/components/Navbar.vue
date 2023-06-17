<template>
    <nav 
                class="navbar navbar-expand-lg"
                :class="[`navbar-${theme}`, `bg-${theme}`]"
            >
                <div class="container-fluid">
                    <a class="navbar-brand" href="#">WebSiteName</a>
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">

                    <li v-for="(page, index) in pages" class="nav-item" :key="index">
                        
                        <div class="dropdown">
                            <button class="dropbtn">Dropdown</button>
                            <div class="dropdown-content">
                                <a href="#">Link 1</a>
                                <a href="#">Link 2</a>
                                <a href="#">Link 3</a>
                            </div>
                        </div>
                        <!-- <a 
                        class="nav-link" 
                        :class="{active: activePage === index}"
                        :href="page.link.url"
                        :title="`this link will take you to the ${page.link.text} page`"
                        @:click.prevent="navLinkClick(index)"
                        >{{ page.link.text }}</a> -->
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
import NavbarLink from './NavbarLink.vue';

export default {
    components: {
                NavbarLink
    },
            props: ['pages', 'activePage', 'navLinkClick'],
            data() {
                return {
                    theme: 'light'
                };
            },
            methods: 
            {
                changeTheme() {
                    this.theme = this.theme == 'light' ? 'dark' : 'light';
                }
            }
        }
</script>

