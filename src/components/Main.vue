/* eslint-disable max-len */
<template>
  <main class="container">
    <div
      v-if="cards.length > 0"
      class="row row-cols-5"
    >
      <div class="col-12">
        <h1>FILMS</h1>
      </div>
      <Card
        v-for="(card, index) in cards"
        :key="index+card.id"
        :datas="card"
      />
      <div class="col-12">
        <h1>TvSeries</h1>
      </div>
      <NewCard
        v-for="(newCard, index) in series"
        :key="index+newCard.id"
        :series="newCard"
      />
    </div>
    <div v-else>
      Nessun risultato
    </div>
  </main>
</template>

<script>
import NewCard from './NewCard.vue';
import Card from './Card.vue';

export default {
  name: 'Main',
  components: {
    Card,
    NewCard,
  },
  props: {
    cards: {
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
