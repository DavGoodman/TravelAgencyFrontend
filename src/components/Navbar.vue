<template>
    <nav 
                class="navbar navbar-expand-lg"
                :class="[`navbar-dark`, `bg-dark`]"
            >
                <div class="container-fluid">
                    <a class="navbar-brand" href="#">MyTravel</a>
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">

                    <li class="nav-item" :key="index">
                        
                        <div class="dropdown">
                            <button class="dropbtn">Get Info</button>
                            <div class="dropdown-content">
                                <a @click="setPosts('https://localhost:7138/api/Invoices/task1A/2')">
                                    1A
                                </a>
                                <a @click="setPosts('https://localhost:7138/api/Invoices/task1B/2015')">
                                    1B
                                </a>
                                <a @click="setPosts('https://localhost:7138/api/Invoices/task1C')">
                                    1C
                                </a>
                                <a @click="setPosts('https://localhost:7138/api/Invoices/task1D')">
                                    1D
                                </a>
                            </div>
                        </div>
                        <div class="dropdown">
                            <button @click="changeVat(true)" class="dropbtn">Vat Varification</button>
                        </div>

                    </li>

                </ul>
                

                
                </div>
            </nav>
</template>

<script>


export default {
    props: ['navLinkClick', "changeVat", "setPosts"],
    data() {
        return {
        };
    },
    methods:{


    }
    }
</script>

