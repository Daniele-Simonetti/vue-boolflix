/* eslint-disable max-len */
<template>
  <main class="container">
    <div
      v-if="cards.length > 0"
      class="row row-cols-5"
    >
      <Card
        v-for="(card, index) in cards"
        :key="index"
        :datas="card"
      />
    </div>
    <div v-else>
      Nessun risultato
    </div>
  </main>
</template>

<script>

import Card from './Card.vue';

export default {
  name: 'Main',
  components: {
    Card,
  },
  props: {
    cards: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  // data() {
  //   return {
  //     query: 'https://api.themoviedb.org/3/search/movie?api_key=071d30c82040935e095df236b751dd91&language=it-IT&query=String',
  //     films: [],
  //     textSearch: '',

  //   };
  // },
  // computed: {
  //   filteredFilms() {
  //     if (this.textSearch.trim() === '') {
  //       return this.films;
  //     }
  // eslint-disable-next-line max-len
  // return this.films.filter((element) => element.title.toLowerCase().includes(this.textSearch.trim().toLowerCase()));
  //   },
  // },
  // created() {

  //   axios.get(this.query)
  //     .then((result) => {
  //       console.log(result.data.results);
  //       this.films = result.data.results;
  //     })
  //     .catch((error) => {
  //       console.log(error);
  //     });
  // },
  // methods: {
  //   searchBar(value) {
  //     console.log('value', value);
  //     this.textSearch = value;
  //     // if (this.textSearch === value) {
  //     //   this.textSearch = '';
  //     // }
  //   },
  // },
};
</script>

<style>

</style>
