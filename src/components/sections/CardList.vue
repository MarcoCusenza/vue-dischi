<template>
  <div class="container">
    <Selector @search="searchGenre" :genres="genres" class="selector-obj" />
    <section class="card-list">
      <div class="container-card" v-for="card in cardsFiltered" :key="card.id">
        <Card class="card" :obj="card" />
      </div>
    </section>
  </div>
</template>

<script>
import axios from "axios";
import Selector from "../commons/Selector.vue";
import Card from "../commons/Card.vue";

export default {
  name: "CardList",
  components: {
    Card,
    Selector,
  },
  data() {
    return {
      genres: ['All'],
      cards: [],
      searchText: "",
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.cards = response.data.response;
        for (let i = 0; i < this.cards.length; i++) {
          if (this.genres.includes(this.cards[i].genre) == false) {
            this.genres.push(this.cards[i].genre);
          }
        }
      })
      .catch(function (error) {
        console.log(error);
      });
  },
  methods: {
    searchGenre(payload) {
      this.searchText = payload;
    },
  },
  computed: {
    cardsFiltered() {
      return this.cards.filter((el) => {
        if(this.searchText == 'All'){
          return el;
        }
        return el.genre.includes(this.searchText); // true/false
      }); // if true conservo altrimenti scarto
    },
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