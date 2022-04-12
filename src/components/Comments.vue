<template>
  <section>
    <Comment 
    v-for="comment in commentList" 
    :key="comment.id" 
    :comment_data="comment" 
    :current_user="currentUser" />
  </section>
</template>

<script>

import Comment from "../components/Comment.vue";

export default {
  data: function () {
    return {
      commentList: [],
      currentUser: {},
    };
  },
  components: {
    Comment,
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      const { comments, currentUser } = require("../data/data.json");
      this.commentList = comments;
      this.currentUser = currentUser;
      console.log(comments);
    }
  },
};
</script>

<style></style>
