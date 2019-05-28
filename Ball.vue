<template lang="pug">
    div.ball(:style="ballStyle")
</template>

<script>

export default {
  name: 'Ball',

  data(){
    return{
      left:0,
      target:200
    }
  },
  methods:{
  animationFn() {
    var queueID;
    const  _animation = () => {
      if (this.left >= this.target) {
        cancelAnimationFrame(queueID);
        return;
      }
      this.left++;
      // ！！！！！这里的属性必须写在行内样式里，这里写死了，注意
      // computed自动计算
      cancelAnimationFrame(queueID);
      queueID = requestAnimationFrame(_animation);
    }
    // 首次渲染
    requestAnimationFrame(_animation);
}
  },
  computed:{
    ballStyle(){
      return `transform:translate(${this.left}px)`
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
