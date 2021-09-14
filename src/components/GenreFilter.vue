<template>
  <select id="filter-genre" v-model="selectedGenre">
    <option value="All">All music</option>
    <option value=""></option>
  </select>
</template>

<script>
export default {
  name: "GenreFilter",
  data() {
    return {
      selectedGenre: "All",
    };
  },
};
</script>

<style lang="scss" scoped>
#filter-genre {
  width: 100px;
}
</style>