<template lang="pug">
    //- npm i pug-plain-loader pug -D
    div#app
        ball(v-for="(item,index) in balls" :initial="item.initial" :target="item.target" @input="balls[index]['initial']++")
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
        balls:[{
            initial:0,
            target:100
        },{
            initial:50,
            target:200
        },]
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
