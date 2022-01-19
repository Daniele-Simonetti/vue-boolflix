<template>
  <div id="app">
    <Header
      @test="test($event)"
    />
    <Main />
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Header,
    Main,
  },
  data() {
    return {
      textSearch: '',
    };
  },
  methods: {
    test(value) {
      console.log('value', value);
      this.textSearch = value;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
