<template>
    <a 
        class="nav-link" 
        :class="activeClasses"
        :href="page.link.url"
        :title="`this link will take you to the ${page.link.text} page`"
        
        >{{ page.link.text }}
    </a> 
</template>

<script>
import { computed } from '@vue/reactivity';

export default {
    props: ['page', 'isActive'],
    computed: {
        activeClasses() {
            return {
                active: this.isActive,
                emphasize: this.isActive
            }
        }
    }
}
</script>