<template>
  <div id="app">
    <Header @searching="search($event)" />
    <Main :cards="cards" />
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Header,
    Main,
  },
  data() {
    return {
      query: 'https://api.themoviedb.org/3/search/',
      api_key: '071d30c82040935e095df236b751dd91',
      language: 'it-IT',
      textSearch: '',
      cards: [],
    };
  },
  methods: {
    search(text) {
      this.textSearch = text;
      this.getFilms();
    },
    getFilms() {
      if (this.textSearch.trim() === '') {
        return this.cards;
      }
      const endpoint = 'movie';
      const parameters = {
        api_key: this.api_key,
        language: this.language,
        query: this.textSearch,
      };
      return axios.get(`${this.query}${endpoint}`, { params: parameters }).then((result) => {
        this.cards = result.data.results;
      }).catch((error) => console.log(error));
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
