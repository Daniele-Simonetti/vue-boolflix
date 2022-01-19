<template>
<div class="container">
  <div class="row">
    <div class="search col">
      <input type="text" id="search" name="search" v-model="inputText" @keyup.enter="test()">
      <button class="btn btn-primary" @click="test()">
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
    test() {
      console.log(this.inputText);
      this.inputText = '';
    },
  },
};
</script>

<style>

</style>
