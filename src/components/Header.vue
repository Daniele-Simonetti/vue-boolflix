/* eslint-disable max-len */
/* eslint-disable max-len */
<template>
  <header>
    <div class="container">
      <div class="row">
        <div class="logo col-6 text-start">
          <img
            src="../assets/img/logo.png"
            alt="logo boolfix"
          >
        </div>
        <div class="search col-6 text-end">
          <input
            v-model="inputText"
            type="text"
            placeholder="Cerca il tuo film"
          >
          <button
            @click="$emit('searching', inputText)"
          >
            Cerca
          </button>
        </div>
      </div>
    </div>
  </header>
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

<style lang="scss" scoped>
header {
  padding-top: 2em;
  background-color: black;
}
  div.logo {
    img {
      width: 30%;
      margin-bottom: 1em;
    }
  }
  div.search {
    input {
      width: 50%;
      height: 42px;
      border-radius: 10px;
      margin-right: 0.2em;
      padding-left: 0.5em;
      font-size: 1.2em;
    }
    button {
      height: 40px;
      background-color: red;
      color: white;
      font-size: 1.3em;
      border: 0;
      border-radius: 5px;
      padding: 0 1em;
    }
  }
</style>
