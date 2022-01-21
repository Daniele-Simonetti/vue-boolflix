/* eslint-disable max-len */
<template>
  <main class="container">
    <div
      v-if="movies.length > 0"
      class="row row-cols-5"
    >
      <div class="col-12">
        <h1>FILMS</h1>
      </div>
      <Card
        v-for="(card, index) in movies"
        :key="index+ '-' +card.id"
        :datas="card"
      />
    </div>
    <div v-else>
      Nessun risultato
    </div>
    <div
      v-if="series.length > 0"
      class="row row-cols-5"
    >
      <div class="col-12">
        <h1>TvSeries</h1>
      </div>
      <Card
        v-for="(card, index) in series"
        :key="index+ '-' +card.id"
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
    movies: {
      type: Array,
      default() {
        return [];
      },
    },
    series: {
      type: Array,
      default() {
        return [];
      },
    },
  },
};
</script>

<style>

</style>
