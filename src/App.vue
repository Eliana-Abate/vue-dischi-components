<template>
  <div id="app">
    <Header />
    <main class="container">
      <Album :arrayFromFather="album" />
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
    };
  },
  methods: {},
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
      });
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
