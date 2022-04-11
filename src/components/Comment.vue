<template>
  <div class="comment-wraper">
    <div class="commentBox">
      <Card>
        <div class="commentBox__score">
          <div class="add">
            <button>
                <img src="@/assets/images/icon-plus.svg" alt="Plus">
            </button>
            
          </div>
          <div class="value">{{ comment_data.score }}</div>
          <div class="sub">
            <button>
                <img src="@/assets/images/icon-minus.svg" alt="Minus">
            </button>
            
          </div>

          
          
        </div>
        <div class="commentBox__content">
          <div class="commentBox__top">
            <picture>
               <source :srcset="getImage(comment_data.user.image.png)" media="(min-width: 600px)">
               <img :src="getImage(comment_data.user.image.png)" :alt="comment_data.user.username"  :title="comment_data.user.username">
            </picture>
            <div class="username">
              {{comment_data.user.username}}
            </div>
            <div class="createdAt">
               {{comment_data.createdAt}}
            </div>
            
          </div>
          <p>
            {{ comment_data.content }}
          </p>

        </div>
        <div class="commentBox__reply-link">
          <button @click="enableComment = !enableComment"> 
            <img src="@/assets/images/icon-reply.svg" alt="Reply">
            Reply
            </button>
        </div>
      </Card>

      <Card v-if="enableComment">
        <RepyBox/>
      </Card>
      <div class="replies">

        
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";
import RepyBox from "./ReplyBox.vue"
export default {
  props: ["comment_data"],
  components: {
    Card,
    RepyBox
  },
  data:function(){
    return{
      enableComment:false
    }
  },
  methods:{
    getImage(FileName){
      return require("@/assets" + FileName.substring(1))
    }
  }
};
</script>

<style lang="scss">
@import "../scss/main.scss";
.commentBox{

  &__score{
    padding: .5rem;
    margin-right: 1rem;
    @include respond(mobile){
      order: 2;
      display: flex;
      padding: 0;
    }
    button{
      border: none;
      cursor: pointer;
    }
    div{
      background-color:$light-grayish_background ;
      text-align: center;
      padding: .8rem 1rem;
      min-width: 4rem;
      @include respond(mobile){
          min-width: 2rem;
          padding: 0.8rem 0.8rem;
      }
      
    }
    :first-child{
        border-top-left-radius: 25%;
        border-top-right-radius: 25%;
      

      @include respond(mobile){
        border-top-left-radius: 0;
        border-top-right-radius: 0;
        border-top-left-radius: 25%;
        border-bottom-left-radius: 25%;
      }
    }
    .value{
      font-weight: 700;
      color:  $moderate-blue;
    }
    :last-child{

        border-bottom-left-radius: 25%;
        border-bottom-right-radius: 25%;
       

      @include respond(mobile){
        border-bottom-left-radius: 0;
        border-bottom-right-radius: 0;
        border-top-right-radius: 25%;
        border-bottom-right-radius: 25%;
      }
      
    }
  }
  &__content{
    margin-bottom: 1.5rem;
  }

  &__top{
    display: flex;
    align-items:center;
    position: relative;
    margin-bottom: .7rem;

     @include respond(mobile){
       font-size: 1.2rem;
     }
    picture{

      @include respond(mobile){
        margin-right:.5rem;
     }
     
      img{
         max-width: 70%;
         @include respond(mobile){
            max-width: 4rem;
        }
       
      }
    }
    .username{
      font-weight: 700;
      margin-right:2rem;
      font-size:1.4rem;
      @include respond(mobile){
        font-size: 1.3rem;
      }
    }
    .createdAt{
        font-size:1.4rem;
        @include respond(mobile){
          font-size: 1.3rem;
        }
    }

  }
  p{
    line-height: 2.5rem;
    @include respond(mobile){
       line-height: 2rem;
    }
  }
  &__reply-link{
      position: absolute;
      top:20%;
      right: 2%;
      @include respond(mobile){
        position: relative;
        order: 3;
        display: flex;
      } 

      button{
        border: none;
        background-color: transparent;
        color: $moderate-blue;
        font-weight: 700;
        cursor: pointer;

        img{
          padding-right: .5rem;
          width: 30%;
          
        }

      }
  }
}

</style>
