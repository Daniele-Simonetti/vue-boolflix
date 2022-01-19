/* eslint-disable max-len */
/* eslint-disable max-len */
<template>
  <main class="container">
    <Search
      @searching="searchBar($event)"
    />
    <div class="row row-cols-5">
      <Card
      v-for="(film, index) in filteredFilms"
      :key="index"
      :title="film.title"
      :originalTitle="film.original_title"
      :language="film.original_language"
      :rating="film.vote_average"
      />
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';
import Search from './Search.vue';

export default {
  name: 'Main',
  components: {
    Card,
    Search,
  },
  data() {
    return {
      query: 'https://api.themoviedb.org/3/search/movie?api_key=071d30c82040935e095df236b751dd91&language=it-IT&query=String',
      films: [],
      textSearch: '',
    };
  },
  computed: {
    filteredFilms() {
      if (this.textSearch.trim() === '') {
        return this.films;
      }
      return this.films.filter((element) => element
        .title
        .toLowerCase()
        .includes(this.textSearch.trim().toLowerCase()));
    },
  },
  created() {
    // "adult": false,
    // "backdrop_path": "/mUyRgpndM4dIpAoLApqrvXPYvaD.jpg",
    // "genre_ids": [
    //    27,
    //    53,
    //    9648
    //  ],
    // "id": 560014,
    // "original_language": "en",
    // "original_title": "The Black String",
    // "overview": "",
    // "popularity": 13.638,
    // "poster_path": "/AmRX8WLUIm2Lm0i6dQrwmBWjW9A.jpg",
    // "release_date": "2018-10-25",
    // "title": "The Black String",
    // "video": false,
    // "vote_average": 5.3,
    // "vote_count": 22
    // },
    axios.get(this.query)
      .then((result) => {
        console.log(result.data.results);
        this.films = result.data.results;
      })
      .catch((error) => {
        console.log(error);
      });
  },
  methods: {
    searchBar(value) {
      console.log('value', value);
      this.textSearch = value;
      // if (this.textSearch === value) {
      //   this.textSearch = '';
      // }
    },
    resetSearchBar(value) {
      this.textSearch = value;
      return this.films;
    },
  },
};
</script>

<style>

</style>
