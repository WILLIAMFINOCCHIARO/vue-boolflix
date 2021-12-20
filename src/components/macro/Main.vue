s (26 sloc) 446 Bytes
<template>
  <main>
    <MovieCard
      v-for="(result, index) in dataShared.searchResults"
      :key="index"
      :infos="result"
    />
  </main>
</template>

<script>
import dataShared from "../../shared/dataShared.js";
import MovieCard from "../sections/ListCard.vue";
export default {
  name: "Main",
  components: {
    MovieCard,
  },
  data() {
    return {
      dataShared,
    };
  },
};
</script>

<style lang="scss" scoped>
</style>