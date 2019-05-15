<template>
  <div class="tree-menu">
    <div :style="indent">{{ content }}</div>
    <Comments
      v-for="comment in comments" 
      :comments="comment.comments" 
      :content="comments.content"
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
        return { transform: `translate(${this.depth * 10}px)` }
      }
    }
  }
</script>