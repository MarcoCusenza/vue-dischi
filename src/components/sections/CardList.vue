<template>
  <Card :obj="cards[0]" />
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

<style>
@import "../../assets/style/partials/variables.scss";
</style>