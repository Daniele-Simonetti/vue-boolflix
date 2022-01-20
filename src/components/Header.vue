/* eslint-disable max-len */
/* eslint-disable max-len */
<template>
  <div class="container">
    <div class="search col">
      <input
        v-model="inputText"
        type="text"
        placeholder="Cerca il tuo film"
      >
      <button
        class="btn btn-primary"
        @click="$emit('searching', inputText)"
      >
        Cerca
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      inputText: '',
    };
  },
};
</script>

<style>

</style>
