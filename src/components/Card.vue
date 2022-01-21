<template>
  <div>
    <div
      class="card "
    >
      <img
        :src="getImg()"
        :alt="datas.title || datas.name"
      >
      <p>
        title: {{ (datas.title) ? datas.title : datas.name }}
      </p>
      <p>
        original title: {{ (datas.original_title) ?datas.original_title : datas.original_name }}
      </p>
      <img
        v-if="getFlag()"
        :src="require(`../assets/img/${datas.original_language}.png`)"
        :alt="datas.original_language"
      >
      <p v-else>
        language: {{ datas.original_language }}
      </p>
      <p>
        {{ datas.vote_average }}
      </p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Card',
  props: {
    datas: Object,
  },
  data() {
    return {
      allLanguages: [
        'en',
        'de',
        'bn',
        'it',
        'ru',
      ],
      noImgAvailable: '../assets/img/placeholder.png',
    };
  },
  methods: {
    getFlag() {
      if (this.allLanguages.includes(this.datas.original_language)) {
        return true;
      }
      return false;
    },
    getImg() {
      if (this.datas.backdrop_path === null) {
        return 'require(noImgAvailable)';
      }
      return this.datas.backdrop_path;
    },
  },
};
</script>

<style lang="sass" scoped>

</style>
