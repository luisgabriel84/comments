<template>
  <div class="component-wraper">
    <Card>
      <div class="comment-wraper">
        <div class="commentBox">
          <Score :score="comment_data.score" />
          <CommentInfo :comment_info="comment_data" :user="current_user"/>
          <Replylink @toggleCommentBox="toggleComment"/>
        </div>
      </div>
    </Card>
    <div class="replyList">
      <Card v-for="reply in comment_data.replies" :key="reply.id">
        <div class="comment-wraper">
          <div class="commentBox">
            <Score :score="reply.score" />
            <CommentInfo :comment_info="reply" :user="current_user"/>
            <Replylink v-if="reply.user.username!==current_user.username"/>
            <Actions v-if="reply.user.username==current_user.username"/>
          </div>
        </div>
      </Card>
    </div>
     <ReplyForm :user="current_user" v-if="enableComment"/>
  </div>
</template>

<script>
import Card from "./Card.vue";
import Score from "./Score.vue";
import CommentInfo from "./CommentInfo.vue";
import Replylink from "./Replylink.vue";
import ReplyForm from "./ReplyForm.vue"
import Actions from "./Actions.vue"

export default {
  props: ["comment_data","current_user"],
  components: {
    Card,
    Score,
    CommentInfo,
    Replylink,
    ReplyForm,
    Actions
  },
  data: function () {
    return {
      enableComment: false,
    };
  },
  methods:{
    toggleComment(){
      this.enableComment = !this.enableComment
    }
  }
};
</script>

<style lang="scss">
@import "../scss/main.scss";
.commentBox {
  display: flex;
  justify-content: space-between;

  @include respond(mobile) {
    flex-wrap: wrap;
  }
}
.replyList {
  margin-left: 4%;
  border-left: 1px solid $light-grayish_blue;
  @include respond(mobile) {
    margin-left: 10%;
  }
}
</style>
