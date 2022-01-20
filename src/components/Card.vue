<template>
  <div
    class="card "
  >
    <p>
      {{ datas.title }}
    </p>
    <p>
      {{ datas.original_title }}
    </p>
    <p>
      {{ datas.original_language }}
    </p>
    <p>
      {{ datas.vote_average }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    datas: Object,
  },
};
</script>

<style>

</style>
