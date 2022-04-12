<template>
  <picture>
    <img
      :src="getImage(picture_data)"
    />
  </picture>
</template>

<script>
export default {
  props:['picture_data'],
  methods: {
    getImage(FileName) {
      return require("@/assets" + FileName.substring(1));
    },
  },
};
</script>

<style lang="scss">
@import "../scss/main.scss";
    picture {
      @include respond(mobile) {
        margin-right: 0.5rem;
      }

      img {
        max-width: 70%;
        @include respond(mobile) {
          max-width: 4rem;
        }
      }
    }
</style>
