<template>
  <header>
    <img src="../../assets/img/logo-small.svg" alt="" />
  </header>
</template>

<script>

export default {
  name: "Header",
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";

header {
  height: 80px;
  line-height: 80px;
  background-color: $darker;
  img {
    height: 65%;
    margin-left: 15px;
    filter: $green-filter;
  }
}
</style>