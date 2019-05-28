<template lang="pug">
    div.ball(:style="ballStyle")
</template>

<script>

export default {
  name: 'Ball',
  props:{
      initial:{
        default:0
      },
      target:{
        default:100
      }
  },
  data(){
    return{
        queueID:0
    }
  },
  methods:{
  animationFn() {
    // var queueID;
    const  _animation = () => {
      if (this.initial >= this.target) {
        cancelAnimationFrame(this.queueID);
        return;
      }
    //   this.initial++;
    this.$emit('input')
      // ！！！！！这里的属性必须写在行内样式里，这里写死了，注意
      // computed自动计算
      cancelAnimationFrame(this.queueID);
      this.queueID = requestAnimationFrame(_animation);
    }
    // 首次渲染
    requestAnimationFrame(_animation);
},
stopAnimation(){
    // 因为随时可能要停止动画，所以这个queueID被拿出去了
    cancelAnimationFrame(this.queueID)
}
  },
  computed:{
    ballStyle(){
      return `transform:translate(${this.initial}px)`
    }
  },
  mounted(){
    this.animationFn()
  }
}
</script>

<style>

.ball{
  width:100px;
  height:100px;
  border-radius:100px;
  background-color:#f69;
}
</style>
