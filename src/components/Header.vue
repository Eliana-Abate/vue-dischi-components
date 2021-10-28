<template>
  <header>
    <div class="container">
      <div class="row">
        <img src="@/assets/images/logo.png" />
        <select
          id="filter-genre"
          v-model="selectedGenre"
          @change="getSelectedGenre"
        >
          <option value="All">All music</option>
          <option
            v-for="(item, index) in arrayGenres"
            :key="index"
            :value="item"
          >
            {{ item }}
          </option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["arrayGenres"],
  components: {},
  data() {
    return {
      selectedGenre: "All",
    };
  },

  methods: {
    getSelectedGenre() {
      this.$emit("valueSelected", this.selectedGenre);
    },
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