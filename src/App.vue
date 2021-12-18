<template>
  <div id="app">
    <Header :genres="genres"/>
    <Main :cards="cards"/>
  </div>
</template>

<script>
import Header from "./components/macro/Header.vue";
import Main from "./components/macro/Main.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      cards: [],
      genres: [],
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
};
</script>

<style lang="scss">
@import "./assets/style/global.scss";
</style>
