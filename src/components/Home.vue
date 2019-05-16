<template>
  <div class="hello">
    <div class="vid">
      <div class='embed-container'>
        <iframe src='https://www.youtube.com/embed/undefined' frameborder='0' allowfullscreen></iframe>
      </div>
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
<style lang="scss">
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

    .embed-container {
      position: relative;
      padding-bottom: 56.25%;
      height: 0;
      overflow: hidden;
      max-width: 100%;
    }
    .embed-container iframe,
    .embed-container object,
    .embed-container embed {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
  }
</style>
