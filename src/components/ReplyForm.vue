<template>
  <Card>
    <div class="replyFormContent">
      <div class="replyFormContent__avatar">
        <Picture :picture_data="user.image.png" />
      </div>
      <div class="replyFormContent__form">
        <textarea></textarea>
      </div>
      <div class="replyFormContent__button">
        <button>REPLY</button>
      </div>
    </div>
  </Card>
</template>

<script>
import Card from "./Card.vue";
import Picture from "./Picture.vue";
export default {
  components: {
    Card,
    Picture,
  },
  props: ["user"],
};
</script>

<style lang="scss">
@import "../scss/main.scss";
.replyFormContent {
  display: flex;
  width: 100%;
  @include respond(mobile) {
    flex-wrap: wrap;
    justify-content: space-between;
  }

  &__avatar {
    flex: 0 0 7%;
    @include respond(mobile) {
      order:2
    }
  }
  &__form {
    flex: 0 0 85%;
    textarea {
      width: 100%;
      height: 8rem;
      border-radius: .8rem;
      padding: 1rem;
       font-family: 'Rubik', sans-serif;
       outline: none;
       font-size: 1.4rem;
    }
      @include respond(mobile) {
        flex: 0 0 100%;
        margin-bottom: 2rem;
    }
  }
  &__button{
    flex: 0 0 8%;
    padding-left:1rem ;
    @include respond(mobile) {
      order:3
    }
    button{
       background-color: $moderate-blue;
       color:$white;
       padding:1rem 1.5rem;
       border: none;
       border-radius: .8rem;
       font-weight: 700;
       font-size: 1.2rem;
       cursor: pointer;
       &:hover{
          background-color: $light-grayish_blue;
       }
    }
  }
}
</style>
