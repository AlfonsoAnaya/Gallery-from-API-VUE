<script lang="ts">
export default {
  data() {
    return {
        photosArr: undefined,
        baseUrl: "https://apis.scrimba.com/unsplash/photos/random/",
        numberOfPhotos: "30",
        theme: "&query=plants"
    };
  },
  methods: {
    fetchData() {
      fetch(`${this.baseUrl}?count=${this.numberOfPhotos}&orientation=portrait`, {
        method: "GET",
      })
        .then((response) => {
          response.json().then((fetchedData) => {
            console.log(fetchedData)
            this.photosArr = fetchedData;
            this.photosArr.sort((a, b) => (a.views < b.views) ? 1 : -1);
          });
        })
        .catch((err) => {
          console.error(err);
        });
    },
  },
  mounted() {
    this.fetchData();
  }
};
</script>

<script setup lang="ts">
import PhotoCard from "./PhotoCard.vue";
</script>

<template>
      <div class="input-bar">
        <p>theme is {{ theme }}</p>
        <p>number of photos is {{ numberOfPhotos }}</p>
        <form class="form" id="form">
            <label><input v-model="theme" id="query-input" type="text" placeholder="plants" /></label>
            <label>No. of photos <input v-model="numberOfPhotos" id="query-number" type="number" placeholder="12" min="1" max="30" /></label>
            <button class="btn" @click="fetchData">Search</button>
        </form>
    </div>
    <div class="grid-container">
    <PhotoCard v-for="item in photosArr"
      :photographer="item.user.name"
      :views="item.views"
      :srcUrl="item.urls.thumb"
      :altDescription="item.alt_description"
      :hrefPhotographer="item.user.links.html" 
      :hrefPhoto="item.urls.small"/>
</div>
</template>

<style scoped>
.grid-container {
    width: 70%;
    margin: 0 auto;
    margin-top: 2em;
    margin-bottom: 3em;
    display: grid;
    justify-content: center;
    gap: 1em;
    grid-template-columns: repeat(auto-fill, 13em);
}
</style>