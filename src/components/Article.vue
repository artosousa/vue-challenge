<template>
    <div>
        this is an article with the id of {{ articleId }}
    </div>
</template>
<script>
    export default {
        name: 'Article',
        props: ["articleId"]
    }
</script>
<style>
</style>