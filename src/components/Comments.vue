<template>
  <div class="tree-menu">
    <div :style="indent" class="tree-menu-comment-content" >
      <div v-if="username" class="tree-menu-comment-username"> <strong>{{ username }} </strong></div>
      <div v-if="date" class="tree-menu-comment-date"><em>{{ moment.unix(date).format('MMM Do YYYY') }}</em></div>
      <div v-if="content" class="tree-menu-comment" v-html="content"></div>
    </div>
    <Comments
      v-for="comment in comments"
      :username="comment.user"
      :date="comment.time"
      :comments="comment.comments"
      :content="comment.content"
      :depth=" depth + 1"
      :key="comment.id"
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
      moment: moment
    }
  },
  name: 'Comments',
  computed: {
    indent () {
      return {
        margin: `0px 0px 0px ${this.depth * 5}px`
      }
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
      margin:-6px 0px 10px 0px;
      padding-bottom: 10px;
      width: 100%;
      border-bottom: 1px solid #d9d9d9;
    }
    .tree-menu-comment{
      background:#e9e9e9;
    }
  }

</style>
