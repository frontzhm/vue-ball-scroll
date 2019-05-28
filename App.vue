<template lang="pug">
    //- npm i pug-plain-loader pug -D
    div#app
        ball(v-for="(item,index) in balls" ref="balls" :initial="item.initial" :target="item.target" @input="balls[index]['initial']++")
        button(@click="stopBall1Fn") 停止球1
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
    stopBall1Fn(){
        // ref在v-for那边的时候是一个数组
        this.$refs.balls[0].stopAnimation()
        console.log(this.balls[0].initial)
    }
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
