<template>
    <div class="post">
        <div class="post_head">
            <h1>{{ post.title }}</h1>
            <div class="genres">
                <span v-for="(genre) in post.genres">{{ genre }}</span>
            </div>
        </div>
        <img :src="[`${post.imgUrl}`]" alt="placeholder">
        <p>{{ post.synopsis }}</p>
    </div>
</template>

<script>

export default {
    props: ['post']
}

</script>