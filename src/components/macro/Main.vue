<template>
  <main>
    <CardList />
  </main>
</template>

<script>
import CardList from "../sections/CardList.vue";

export default {
  name: "Main",
  components: {
    CardList,
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";
</style>