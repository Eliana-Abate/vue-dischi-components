<template>
  <header>
    <div class="container">
      <div class="row">
        <img src="@/assets/images/logo.png" />
        <select id="filter-genre" v-model="selectedGenre">
          <option value="All">All music</option>
          <option value=""></option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  components: {},
  data() {
    return {
      selectedGenre: "All",
    };
  },
};
</script>

<style scoped lang="scss">
header {
  background-color: #2e3a46;
  height: 70px;
  padding: 10px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  .row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 10px;
    img {
      height: 50px;
    }
  }
}

#filter-genre {
  width: 100px;
}
</style>