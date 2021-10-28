<template>
  <div id="app">
    <Header :arrayGenres="genres" @valueSelected="getFilteredValue" />
    <main class="container">
      <Album :arrayAlbum="getFilteredValue(album)" />
    </main>
  </div>
</template>


<script>
import axios from "axios";
import Header from "@/components/Header.vue";
import Album from "@/components/Album.vue";

export default {
  name: "App",
  components: {
    Header,
    Album,
  },
  data() {
    return {
      album: [],
      genres: [],
      genreValue: "",
    };
  },
  methods: {
    getFilteredValue(array) {
      if (this.genreValue == array.genre) return array;
    },
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        const response = res.data.response;
        console.log(response);

        response.sort((a, b) => {
          return a.year - b.year;
        });

        this.album = response;

        this.album.forEach((item) => {
          if (!this.genres.includes(item.genre)) {
            this.genres.push(item.genre);
          }
        });
      });
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
