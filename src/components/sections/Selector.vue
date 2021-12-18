<template>
  <section class="container-selector">
    <select name="selector" id="selector">
      <option v-for="(genre, i) in genres" :key="i" value="genre">
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
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";
.container-selector {
  select {
    min-width: 120px;
    height: 30px;
    background-color: $dark;
    box-shadow: none;
    border: 2px solid $lighter;
    border-radius: 5px;
    font-family: "Open Sans", sans-serif;
    font-weight: bold;
    font-size: 16px;
    color: $lighter;

    option {
      font-weight: bold;
    }
  }
}
</style>