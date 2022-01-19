<template>
  <div
    class="card "
  >
    <p>
      {{title}}
    </p>
    <p>
      {{originalTitle}}
    </p>
    <p>
      {{language}}
    </p>
    <p>
      {{rating}}
    </p>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    title: {
      type: String,
      required: true,
    },
    originalTitle: {
      type: String,
      required: true,
    },
    language: {
      type: String,
      required: true,
    },
    rating: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style>

</style>
