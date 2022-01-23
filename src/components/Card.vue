/* eslint-disable max-len */
<template>
  <div
    class="card "
  >
    <div
      class="front-img"
      @mouseover="show = true"
    >
      <img
        v-show="show === false"
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
        title: {{ (datas.title) ? datas.title : datas.name }}
      </p>
      <p>
        original title: {{ (datas.original_title) ? datas.original_title : datas.original_name }}
      </p>
      <img
        v-if="getFlag()"
        :src="require(`../assets/img/${datas.original_language}.png`)"
        :alt="datas.original_language"
      >
      <p v-else>
        language: {{ datas.original_language }}
      </p>
      <p>
        vote-average: {{ roundNumber(datas.vote_average) }}
      </p>
      <i
        v-for="n in 5"
        :key="n"
        :class="(n <= roundNumber(datas.vote_average)) ? 'fas fa-star' : 'far fa-star'"
      />
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
img {
  width: 100%;
}

</style>
