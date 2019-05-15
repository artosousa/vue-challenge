<template>
  <div class="tree-menu">
    <div :style="indent">{{ label }}</div>
    <Comments
      v-for="node in nodes" 
      :nodes="node.nodes" 
      :label="node.label"
      :depth=" depth + 1"
    >
    </Comments>
  </div>
</template>
<script>
  export default { 
    props: [ 'label', 'nodes', 'depth' ],
    name: 'Comments',
    computed: {
      indent() {
        return { transform: `translate(${this.depth * 10}px)` }
      }
    }
  }
</script>