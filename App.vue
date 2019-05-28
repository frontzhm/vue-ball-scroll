<template lang="pug">
    //- npm i pug-plain-loader pug -D
    div#app
        ball
        //- <button @click="getPosition">获取球1的位置</button>
        //-<button @click="stop">停止球1的位置</button>
</template>

<script>
import Ball from './Ball.vue'

export default {
  name: 'app',
  components: {
    Ball
  },
  data(){
    return{

    }
  },
  methods:{

  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
