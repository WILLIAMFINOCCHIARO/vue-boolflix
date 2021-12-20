<template>
  <div class="card">
    <h2>{{ infos.title }}</h2>
    <h3>{{ infos.original_title }}</h3>
    <span v-if="infos.original_language == ''">Lingua non disponibile</span>
    <p class="Vote">{{ infos.vote_average }}</p>
  </div>
</template>

<script>
export default {
  name: "ListCard",
  props: {
    infos: Object,
  },
};
</script>
