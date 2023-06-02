<script setup lang="ts">
defineProps<{
    photographer: string;
    views: number;
    srcUrl: string;
    altDescription: string;
    hrefPhotographer: string;
    hrefPhoto: string;
}>()
</script>

<template v-for="item in items">
<div class="photo-card">
    <div class="image-container">
        <a target="blank" :href="hrefPhoto">
            <img :src="srcUrl" :alt="altDescription"
            class="image">
        </a>

    </div>
    <figcaption>
        <p class="author">Photo by: {{ photographer }} -
            <a class="link" target="blank" :href="hrefPhotographer">Unsplash profile</a>
        </p>
        <p class="views"> Views: {{views}}</p>
    </figcaption>
</div>
</template>

<style scoped>
.photo-card {
    width:13em;
    height:21.1em;
}

.image-container {
    width: 100%;
    height: 18em;
    overflow: hidden;
    transition: 0.3s ease;
}

.image-container:hover {
    opacity: .8;
}

.image {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.author, .views {
    font-family: Helvetica, Arial, sans-serif;
    margin: 0;
}

.author {
    font-size: .8em;
    opacity: .9;
    margin: .2em 0;
}

.views {
    font-size: .8em;
    opacity: .8;
}

.link {
    color: inherit;
    opacity: .6;
    text-decoration: none;
}

.link:hover {
    cursor: pointer;
    opacity: .9;
}
</style>