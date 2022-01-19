<template>
  <div></div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Main',
  data() {
    return {
      query: 'https://api.themoviedb.org/3/search/movie?api_key=071d30c82040935e095df236b751dd91&language=it-IT&query=String',
      films: [],
    };
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
};
</script>

<style>

</style>
