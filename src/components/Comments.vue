<template>
  <div class="tree-menu">
    <div :style="indent">{{ parent_comments }}</div>
    <Comments
      v-for="child_comment in child_comments" 
      :child_comments="child_comment.child_comments" 
      :parent_comments="child_comments.parent_comments"
      :depth=" depth + 1"
    >
    </Comments>
  </div>
</template>
<script>
  export default { 
    props: [ 'parent_comments', 'child_comments', 'depth' ],
    name: 'Comments',
    computed: {
      indent() {
        return { transform: `translate(${this.depth * 10}px)` }
      }
    }
  }
</script>