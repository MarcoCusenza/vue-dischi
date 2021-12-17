<template>
  <a class="card" href="#">
    <img :src="obj.poster" :alt="obj.title" />
    <h3>{{obj.title}}</h3>
    <div class="artist">{{obj.author}}</div>
    <div class="year">{{obj.year}}</div>
  </a>
</template>

<script>
export default {
  name: "Card",
  props: {
    obj: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";

.card {
  &:hover img {
    opacity: 1;
    transition: 0.5s;
  }
  img {
    width: 80%;
    opacity: 0.9;
  }
  .text {
    width: 80%;
    margin-top: 5px;
    color: $light-text;
    font-size: 13px;
    text-transform: uppercase;
  }
}
</style>