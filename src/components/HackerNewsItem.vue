<template>
    <div class="news-item" >
        <router-link :to="{ name: 'Article', params: { articleId: article.id }}">
            <h2>{{ article.title }}</h2>
            <small>{{ article.points }} points | Article by: <strong>{{ article.user }}</strong> | Posted:  {{ moment.unix(article.time).format('DD/MM/YYYY') }} | Source: {{ article.domain }}</small>
        </router-link>
    </div>
</template>

<script>
    const moment = require('moment')
    export default {
        name: 'HackerNewsItem',
        props: ["article"],
        data() {
            return{
                moment:moment
            }
        }
    }
</script>
<style scoped lang="scss">
    .news-item{
        padding-bottom:20px;
        border-bottom: 1px dashed #e9e9e9;
        padding-top: 20px;
        
        h2{
            padding: 0px;
            margin: 0px;
        }

        &:hover{
            cursor: pointer;
            background:lemonchiffon;
        }
    }
</style>
