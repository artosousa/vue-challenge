<template>
  <div class="tree-menu">
    <div :style="indent" class="tree-menu-comment-content" >
      <div class="tree-menu-comment-username"> <strong>{{ username }} </strong></div>
      <div class="tree-menu-comment-date"><em>{{ moment.unix(date).format('MMM Do YYYY') }}</em></div>

      <div class="tree-menu-comment" v-html="content"></div>
    </div>
    <Comments 
      v-for="comment in comments"
      :username="comment.user"
      :date="comment.time"
      :comments="comment.comments" 
      :content="comment.content"
      :depth=" depth + 1"
    >
    </Comments>
  </div>
</template>
<script>
  const moment = require('moment')
  export default { 
    props: [ 'content', 'comments', 'username', 'date', 'depth' ],
    data () {
        return {
            moment:moment
        }
    },
    name: 'Comments',
    computed: {
      indent() {
        return { margin: `0px 0px 0px ${this.depth * 10}px` }
      }
    }
  }
</script>
<style scoped lang="scss">
  .tree-menu{
    padding:10px;
    background:#e9e9e9;
    font-size: 14px;
    line-height: 18px;

    
    .tree-menu-comment-username{
      margin: 0px;
    }
    .tree-menu-comment-date{
      font-size: 12px;
      margin:0px;
      padding-bottom: 10px;
      width: 100%;
      border-bottom: 1px solid #d9d9d9;
      margin-top: -6px;
    }
  }
  
  
</style>
