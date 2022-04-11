<template>
  <section>
    <div v-for="(comment, index) in commentList" :key="index">
        
          <Comment :comment_data = "comment"></Comment>

    </div>
  </section>
</template>

<script>

import Comment from './Comment.vue' 

export default {
    data:function(){
      return{
        commentList:[
        ],
        currentUser:{}
      }
    },
    components:{
        Comment
    },
    created(){
      this.fetchData()
    },
    methods:{

      fetchData(){
        const {comments, currentUser} = require('../data/data.json')
        this.commentList = comments
        this.currentUser = currentUser
        console.log(comments)
      }
    }
}
</script>

<style>

</style>