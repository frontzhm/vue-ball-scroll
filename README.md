# vue-ball-scroll

必须按照vue-cli

```shell
sudo npm install @vue/cli @vue/cli-service-global -g
npm i pug-plain-loader pug -D
```

然后

```shell
vue serve
```

可以[看以往的版本](https://github.com/frontzhm/vue-ball-scroll/commits/master)

## 动画的重点代码

```js
function animationFn(el, initial, target) {
  var queueID;
  var accur = initial;
  function _animation() {
    if (accur >= target) {
      cancelAnimationFrame(queueID);
      return;
    }
    accur++;
    // ！！！！！这里的属性必须写在行内样式里，这里写死了，注意
    el.style.transform = `translate(${accur}px)`;
    cancelAnimationFrame(queueID);
    queueID = requestAnimationFrame(_animation);
  }
  // 首次渲染
  requestAnimationFrame(_animation);
}
```

## 其他的点

* vue的子组件想改变父组件的值，on,emit
* vue的父组件想调用子组件的方法，$refs.xx.fn()
* v-for的ref是数组