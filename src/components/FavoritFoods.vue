<template>
  <div class="hello">
    <p>{{ tacos }}</p>
    <p>{{ talames }}</p>
    <p>{{ pizza }}</p>
    <p>{{ pasta }}</p>
  </div>
</template>

<script>
export default {
  name: "FavoritFood",
  props: {
    tacos: String,
    tamales: String,
    pizza: String,
    pasta: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
