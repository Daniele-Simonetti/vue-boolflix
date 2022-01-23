/* eslint-disable max-len */
<template>
  <main class="container-fluid">
    <div class="col-12">
      <h1>FILMS</h1>
    </div>
    <div
      v-if="movies.length > 0"
      class="row row-cols-6 films"
    >
      <Card
        v-for="(card, index) in movies"
        :key="index+ '-' +card.id"
        :datas="card"
      />
    </div>
    <div
      v-else
      class="noFound"
    >
      Nessun risultato
    </div>
    <div class="col-12">
      <h1>TvSeries</h1>
    </div>
    <div
      v-if="series.length > 0"
      class="row row-cols-6 series"
    >
      <Card
        v-for="(card, index) in series"
        :key="index+ '-' +card.id"
        :datas="card"
      />
    </div>
    <div
      v-else
      class="noFound"
    >
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

<style lang="scss" scoped>
.row {
  justify-content: center;
}
.noFound {
  font-size: 3em;
  margin-top: 5em;
}
h1 {
  margin-top: 1em;
  font-size: 4em;
  font-weight: bold;
  color: red;
}
.row {
  margin-top: 3em;
}
.films {
  height: 50vh;
  overflow: auto;
}
.series {
  height: 50vh;
  overflow: auto;
}
</style>
