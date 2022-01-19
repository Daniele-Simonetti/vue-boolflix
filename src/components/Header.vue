/* eslint-disable max-len */
/* eslint-disable max-len */
<template>
<div class="container">
  <div class="row">
    <div class="search col">
      <input
      type="text"
      v-model="inputText"
      @keyup.enter="$emit('test', inputText)">
      <button class="btn btn-primary" @click="$emit('test', inputText)">
        Cerca
      </button>
    </div>
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
  methods: {
  },
};
</script>

<style>

</style>
