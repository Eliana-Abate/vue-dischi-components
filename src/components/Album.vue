<template>
  <section id="album-container">
    <AlbumCard v-for="(disc, index) in arrayAlbum" :key="index" :disc="disc" />
  </section>
</template>

<script>
import AlbumCard from "@/components/AlbumCard.vue";

export default {
  name: "Album",
  props: ["arrayAlbum"],
  components: {
    AlbumCard,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
#album-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>