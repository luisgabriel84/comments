<template>
  <div class="commentBox__scoreControls">
    <div class="add">
      <button>
        <img src="@/assets/images/icon-plus.svg" alt="Plus" />
      </button>
    </div>
    <div class="value">{{score}}</div>
    <div class="sub">
      <button>
        <img src="@/assets/images/icon-minus.svg" alt="Minus" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props:["score"]
};
</script>

<style lang="scss">
@import "../scss/main.scss";
.commentBox {
  &__scoreControls {
    padding: 0.5rem;
    margin-right: 1rem;
    @include respond(mobile) {
      order: 2;
      display: flex;
      padding: 0;
    }
    button {
      border: none;
      cursor: pointer;
    }
    div {
      background-color: $light-grayish_background;
      text-align: center;
      padding: 0.8rem 1rem;
      min-width: 4rem;
      @include respond(mobile) {
        min-width: 2rem;
        padding: 0.8rem 0.8rem;
      }
    }
    :first-child {
      border-top-left-radius: 25%;
      border-top-right-radius: 25%;

      @include respond(mobile) {
        border-top-left-radius: 0;
        border-top-right-radius: 0;
        border-top-left-radius: 25%;
        border-bottom-left-radius: 25%;
      }
    }
    .value {
      font-weight: 700;
      color: $moderate-blue;
    }
    :last-child {
      border-bottom-left-radius: 25%;
      border-bottom-right-radius: 25%;

      @include respond(mobile) {
        border-bottom-left-radius: 0;
        border-bottom-right-radius: 0;
        border-top-right-radius: 25%;
        border-bottom-right-radius: 25%;
      }
    }
  }
}
</style>
