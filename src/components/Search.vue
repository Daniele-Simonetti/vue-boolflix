<template>
  <div class="search col">
      <input
      type="text"
      v-model="inputText"
      >
      <button class="btn btn-primary" @click="$emit('test', inputText)">
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
};
</script>

<style>

</style>
