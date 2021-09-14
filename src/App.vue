<template>
  <div id="app">
    <Header />
    <main class="container">
      <Album @arrayFromAlbum="getFullArray" />
    </main>
  </div>
</template>


<script>
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
      fullArray: [],
    };
  },
  methods: {
    getFullArray(albums) {
      return (this.fullArray = albums);
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
