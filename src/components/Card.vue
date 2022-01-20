<template>
  <div>
    <div
      class="card "
    >
      <p>
        {{ datas.title }}
      </p>
      <p>
        {{ datas.original_title }}
      </p>
      <i :class="'flag flag-' + getFlag(datas.original_language)" />
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
  methods: {
    getFlag(lang) {
      if (lang === 'en') {
        return 'us';
      }
      return lang;
    },
  },
};
</script>

<style lang="sass" scoped>
  @import '~mdb-ui-kit/css/mdb.min.css'

</style>
