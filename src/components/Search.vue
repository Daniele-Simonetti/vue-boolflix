<template>
  <div class="search col">
      <input
      type="text"
      placeholder="Cerca il tuo film"
      v-model="inputText"
      >
      <button class="btn btn-primary" @click="$emit('searching', inputText)">
        Cerca
      </button>
    </div>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
      inputText: '',
    };
  },
  methods: {
  },
};
</script>

<style>

</style>
