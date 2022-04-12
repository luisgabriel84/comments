<template>
  <div class="commentBox__reply-link">
    <button @click="$emit('toggleCommentBox')">
      <img src="@/assets/images/icon-reply.svg" alt="Reply" />
      Reply
    </button>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "../scss/main.scss";
.commentBox {
&__reply-link {
    @include button-bar();
    }
}
</style>
