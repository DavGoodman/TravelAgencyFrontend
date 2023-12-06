<template>
    <div class="container">
        <h1 class="page-title">MyTravel</h1>
        <VatVerification v-if="vat"> </VatVerification>
        <div class="posts-container" v-else>
            <InfoCard
                v-for="(post, index) in posts"
                :key="index"
                :post="post">

            </InfoCard>
        </div>
        
    </div>
</template>

<script>

import InfoCard from './InfoCard.vue';
import VatVerification from './VatVerification.vue';

export default {
    components: {
        InfoCard,
        VatVerification
    },
    props: ['page', 'posts', "vat"],
    methods:{
        
    }
}
</script>