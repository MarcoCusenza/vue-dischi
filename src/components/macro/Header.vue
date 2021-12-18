<template>
  <header>
    <img src="../../assets/img/logo-small.svg" alt="" />
    <Selector :genres="genres"/>
  </header>
</template>

<script>
import Selector from "../sections/Selector.vue";

export default {
  name: "Header",
  components: {
    Selector,
  },
  props: {
    genres: [],
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";

header {
  height: 80px;
  line-height: 80px;
  background-color: $darker;
  position: relative;
  text-align: center;
  img {
    height: 65%;
    margin-left: 15px;
    filter: $green-filter;
    position: absolute;
    left: 6px;
    top: 50%;
    transform: translate(0, -50%);
  }
}
</style>