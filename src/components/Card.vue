/* eslint-disable max-len */
/* eslint-disable max-len */
<template>
  <div
    class="card "
  >
    <div
      v-show="show === false"
      class="front-img"
      @mouseover="show = true"
    >
      <img
        :src="getImg()"
        :alt="datas.title || datas.name"
      >
    </div>
    <div
      v-show="show === true"
      class="description"
      @mouseleave="show = false"
    >
      <p>
        <span>Title:</span> {{ (datas.title) ? datas.title : datas.name }}
      </p>
      <p v-if="datas.original_title != datas.title">
        <span>original title:</span> {{
          (datas.original_title)
            ?
              datas.original_title : datas.original_name
        }}
      </p>
      <p v-if="getFlag()">
        <span>Language:</span>
        <img
          :src="require(`../assets/img/${datas.original_language}.png`)"
          :alt="datas.original_language"
          class="flag"
        >
      </p>
      <p v-else>
        <span>Language:</span> {{ datas.original_language }}
      </p>
      <p
        class="Overview"
      >
        <span>Overview:</span> {{ (datas.overview != '')
          ?
            datas.overview :
            'no overview avilable' }}
      </p>
      <!-- <p v-else>
        <span>Overview:</span> no overwiev avilable
      </p> -->
      <p>
        <span>vote-average:</span>
        <i
          v-for="n in 5"
          :key="n"
          :class="(n <= roundNumber(datas.vote_average)) ? 'fas fa-star' : 'far fa-star'"
        />
      </p>
    </div>
    <!-- <div class="text">
      </div> -->
  </div>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css';

export default {
  name: 'Card',
  props: {
    datas: Object,
  },
  data() {
    return {
      allLanguages: [
        'en',
        'de',
        'bn',
        'it',
        'ru',
        'fr',
        'zh',
        'ja',
        'cn',
        'te',
        'kn',
        'fi',
        'pl',
        'tr',
        'nl',
        'ta',
        'et',
        'no',
        'sv',
        'pt',
        'th',
        'da',
        'cs',
        'sr',
        'es',
      ],
      show: false,
    };
  },
  methods: {
    getFlag() {
      if (this.allLanguages.includes(this.datas.original_language)) {
        return true;
      }
      return false;
    },
    getImg() {
      if (this.datas.backdrop_path === null) {
        // eslint-disable-next-line global-require
        return require('../assets/img/placeholder.png');
      }
      return `https://image.tmdb.org/t/p/w342/${this.datas.backdrop_path}`;
    },
    roundNumber(number) {
      // number corrisponde al mio data del voto medio
      console.log(number, number / 2);
      // eslint-disable-next-line max-len
      // con questa formula dico alla mia funzione di prendere il data e dividerlo per tue, arrotondandolo= da 1 a 10 a 1 a 5
      return Math.round(number / 2);
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  font-size: 1em;
  text-align: left;
  margin: 1em;
  background-color: black;
  color: white;
  border: 3px solid white;
  height: 293.66px;
  padding: 0;
  div.front-img {
    height: 100%;
    img {
      height: 100%;
    }
  }
  div.description {
    margin: 0 0.5em;
  }
  p {
    margin-top: 0.6em;
  }
  img.flag {
    width: 10%;
    margin-left: 0.5em;
  }
  span {
    font-weight: bold;
  }
  p.Overview {
    height: 100px;
    overflow: auto;
  }
}
img {
  width: 100%;
}

</style>
