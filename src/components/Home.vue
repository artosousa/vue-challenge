<template>
  <div class="hello">
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
      msg: `Use navigation above to see experience completed challenges`
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
</style>
