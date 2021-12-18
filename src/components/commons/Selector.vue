<template>
  <section class="container-selector">
    <select name="selector" id="selector" v-model="searchText">
      <option
        v-for="(genre, i) in genres"
        :key="i"
        :value="genre"
        @click.prevent="$emit('search', genre)"
      >
        {{ genre }}
      </option>
    </select>
  </section>
</template>

<script>
export default {
  name: "Selector",
  props: {
    genres: [],
  },
  data() {
    return {
      searchText: "",
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";
.container-selector {
  select {
    min-width: 120px;
    height: 30px;
    padding: 5px;
    background-color: $dark;
    box-shadow: none;
    border: none;
    border-radius: 5px;
    font-family: "Open Sans", sans-serif;
    font-weight: bold;
    font-size: 16px;
    color: $lighter;

    option {
      font-weight: bold;
      padding:5px;
    }
  }
}
</style>