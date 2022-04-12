<template>
  <div id="app" class="appContainer">
    <Comments/>
  </div>
</template>

<script>
import Comments from './components/Comments.vue'
export default {
  name: 'App',
  components: {
    Comments


  }
}
</script>

<style lang="scss">
@import "./scss/main.scss";
.appContainer{
  max-width:1200px ;
  margin: auto;
}

</style>
