<template>
  <div class="box-wrapper">
      <slot>my content here</slot>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import "../scss/main.scss";
.box-wrapper{
    background-color: $white;
    padding:2rem;
    border-radius: 1rem;
    color:$grayish-blue;
    margin:2rem;
    display: flex;
    position: relative;
    @include respond(mobile){
      flex-wrap: wrap;
      justify-content: space-between;
    }
}

</style>