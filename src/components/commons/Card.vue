<template>
  <a class="card" href="#">
    <img :src="obj.poster" :alt="obj.title" />
    <div class="text">
      <h3>{{ obj.title }}</h3>
      <div class="details">
        <div class="artist">{{ obj.author }}</div>
        <div class="year">{{ obj.year }}</div>
      </div>
    </div>
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
  text-decoration: none;
  &:hover img {
    opacity: 1;
  }
  img {
    width: 80%;
    opacity: 0.9;
    transition: 0.5s;
  }
  .text {
    width: 80%;
    margin: 0 auto;
    text-align: center;
    margin-top: 5px;
    color: $light-text;
    h3 {
      text-transform: uppercase;
      font-size: 20px;
      margin: 15px 0 15px 0;
    }
    .details {
      color: $medium-text;
      font-size: 17px;
    }
  }
}
</style>