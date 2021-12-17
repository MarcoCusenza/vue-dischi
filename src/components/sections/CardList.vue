<template>
  <div class="container">
    <section class="card-list">
      <div class="container-card" v-for="card in cards" :key="card.id">
        <Card class="card" :obj="card" />
      </div>
    </section>
  </div>
</template>

<script>
import Card from "../commons/Card.vue";
import axios from "axios";

export default {
  name: "CardList",
  components: {
    Card,
  },
  data() {
    return {
      cards: {},
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.cards = response.data.response;
      })
      .catch(function (error) {
        console.log(error);
      });
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";

.container {
  padding: 50px 0;
  text-align: center;
  .card-list {
    display: grid;
    grid-template-columns: 20% 20% 20% 20% 20%;
    .container-card {
      width: 200px;
      margin: 0 auto;
      background-color: $darker;
      padding: 20px 10px 10px 10px;
      margin: 12px 0;
    }
  }
}
</style>