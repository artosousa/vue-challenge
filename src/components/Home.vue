<template>
  <div class="hello">
    <div class="vid">
      <iframe width="560" height="315" src="https://www.youtube.com/embed/9pOo4rf544A" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
    <h1>{{ Title }}</h1>
    <p> {{ msg }}</p>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      Title: `Welcome to Arthur's Vue.js Challenge`,
      msg: `Use navigation above to experience completed challenges`
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
  .vid{
    max-width: 650px;
    position: relative;
    margin: 0px auto 25px auto;
  }
</style>
