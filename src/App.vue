<template>
  <div id="app">
    <Header :arrayGenres="genres" @valueSelected="getFilteredValue" />
    <main class="container">
      <Album :arrayAlbum="albumGenreFiltered" />
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
      genreValue: "All",
    };
  },
  computed: {
    albumGenreFiltered: function () {
      if (this.genreValue == "All") return this.album;
      return this.album.filter((item) => {
        if (item.genre == this.genreValue) return true;
      });
    },
  },
  methods: {
    getFilteredValue(genre) {
      this.genreValue = genre;
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
