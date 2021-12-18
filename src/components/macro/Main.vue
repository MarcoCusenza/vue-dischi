<template>
  <main>
    <CardList :cards="cards"/>
  </main>
</template>

<script>
import CardList from '../sections/CardList.vue'

export default {
  name: 'Main',
  components: {
    CardList,
  },
  props:{
    cards: [],
  }
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";

</style>