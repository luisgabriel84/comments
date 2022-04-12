<template>
  <div class="commentBox__content">
    <div class="commentBox__top">
      <Picture :picture_data="comment_info.user.image.png"/>
      <div class="username">
        {{ comment_info.user.username }}
      </div>

      <div class="badge" v-if="comment_info.user.username== user.username">
        <span class="badge__you">you</span>
      </div>

      <div class="createdAt">
        {{ comment_info.createdAt }}
      </div>
    </div>
    <p>
      {{ comment_info.content }}
    </p>
  </div>
</template>

<script>
import Picture from "./Picture.vue"
export default {
  props: ["comment_info","user"],
  components:{
    Picture
  },
  methods: {
    getImage(FileName) {
      return require("@/assets" + FileName.substring(1));
    }
  },
};
</script>

<style lang="scss">
@import "../scss/main.scss";
.commentBox {
  &__top {
    display: flex;
    align-items: center;
    position: relative;
    margin-bottom: 0.7rem;

    @include respond(mobile) {
      font-size: 1.2rem;
    }

    .username {
      font-weight: 700;
      margin-right: 1.5rem;
      font-size: 1.4rem;
      @include respond(mobile) {
        font-size: 1.3rem;
      }
    }
    .badge{
       margin-right: 1.5rem;
       font-size: 1.2rem;
       color:$white;
       
       &__you{
         background-color: $moderate-blue;
         padding: .2rem .5rem;
       }
    }
    .createdAt {
      font-size: 1.4rem;
      @include respond(mobile) {
        font-size: 1.3rem;
      }
    }
  }
  &__content {
    margin-bottom: 2rem;
  }
}
</style>
