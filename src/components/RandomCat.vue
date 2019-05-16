<template>
    <div class="kitty-content">
        <h1> {{ msg}} </h1>
        <div id="cat-imgs">
            <span v-if="!catImg" > Loadding Kitten ...</span>
            <img class="full-width" v-else v-bind:src="catImg" @click="fetchImg">
        </div>
        <button @click="fetchImg">{{ btnText }}</button>
    </div>
</template>

<script>
import axios from 'axios'
const catUrl = 'https://aws.random.cat/meow'
export default {
  name: 'RandomCat',
  beforeMount () {
    this.fetchImg()
  },
  data () {
    return {
      msg: 'Random Cat Generator',
      btnText: 'More Kittens!',
      catImg: '',
      fetchImg: () => {
        axios.get(catUrl)
          .then(res => {
            this.catImg = res.data.file
          })
          .catch(err => console.log(err))
        console.log('ive been clicked')
      }
    }
  }
}
</script>
<style scoped lang="scss">
    .kitty-content{
        max-width: 860px;
        position: relative;
        margin: 0px auto;
        h1{
            padding-bottom: 15px;
        }
        #cat-imgs{
            position: relative;
            margin: 0px auto;
            img.full-width{
                width: 100%;
                height: auto;
                cursor: pointer;
            }
            img.loading{
              width:200px !important;
            }
        }
        button{
            display: block;
            cursor: pointer;
            width:100%;
            margin: 20px auto;
            text-align: center;
            color:#fff;
            text-decoration: none;
            background-color: #429000;
            padding:10px 5px;
            -webkit-border-radius: 5px;
            -moz-border-radius: 5px;
            border-radius: 5px;
            -webkit-box-sizing: border-box;
            -moz-box-sizing: border-box;
            box-sizing: border-box;
            border: 5px solid #429000;

            &:hover{
                background-color: #396a0f;
                border: 5px solid #396a0f;
            }
            &:active{
                margin-top: 21px;
            }
        }
    }
</style>
