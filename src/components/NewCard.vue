<template>
  <div
    class="card "
  >
    <p>
      {{ series.name }}
    </p>
    <p>
      {{ series.original_name }}
    </p>
    <i :class="'flag flag-' + getFlag(series.original_language)" />
    <p>
      {{ series.vote_average }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'NewCard',
  props: {
    series: Object,
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

<style lang="scss" scoped>
@import '~mdb-ui-kit/css/mdb.min.css'
</style>
