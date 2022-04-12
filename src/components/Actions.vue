<template>
  <div class="commentBox__actions">
    <button>
      <img src="@/assets/images/icon-delete.svg" alt="Delete" />
      Delete
    </button>
    <button>
      <img src="@/assets/images/icon-edit.svg" alt="Edit" />
      Edit
    </button>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "../scss/main.scss";
.commentBox__actions {
 @include button-bar();
}
</style>
