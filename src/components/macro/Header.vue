<template>
  <header>
    <div class="search">
      <input type="text" v-model="searchText" @keyup.enter="onSearchMovie()" />
      <button @click="onSearchMovie()">Cerca</button>
    </div>
  </header>
</template>

<script>
import axios from "axios";
import dataShared from "../../shared/dataShared.js";
export default {
  name: "Header",
  data() {
    return {
      dataShared,
      searchText: "",
    };
  },
  methods: {
    onSearchMovie: function () {
      if (this.searchText == "") {
        alert("Inserisci un valore corretto!");
      } else {
        axios
          .get("https://api.themoviedb.org/3/search/movie", {
            params: {
              api_key: "e8e9c5d33202e3f3cb15a4da758fdf65",
              query: this.searchText,
              language: "it-IT",
            },
          })
          .then(function (response) {
            dataShared.searchResults = response.data.results;
          })
          .catch(function (error) {
            console.log(error);
          });
      }
    },
  },
};
</script>
