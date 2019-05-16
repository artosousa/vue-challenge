<template>
  <div class="tree-menu">
    <div :style="indent" class="single-comment" v-html="content" ></div>
    <Comments 
      v-for="comment in comments"
      :comments="comment.comments" 
      :content="comment.content"
      :depth=" depth + 1"
    >
    </Comments>
  </div>
</template>
<script>
  export default { 
    props: [ 'content', 'comments', 'depth' ],
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
    border: 1px solid #c0c0c0;
    font-size: 14px;
    line-height: 18px;
    .single-comment{
      padding:10px 0px 15px 0px;
      
    }
  }
  
  
</style>
