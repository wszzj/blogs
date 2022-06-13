# Vue的修饰符
1. 事件修饰符
在事件处理中，event.preventDefault()用于取消元素默认事件，event.stopPropagation()用于组织元素事件冒泡，都是常用的事件需求。Vue提供了简写的修饰符：
```
<a v-on:click.stop="xxx"></a>//阻止单击事件传播
<form v-on:submit.prevent="onSubmit"></form>//提交事件不再重载页面
<a v-on:click.once="do"></a>//单击事件只会触发一次
```
2. 按键修饰符
当需要监听键盘事件时，需要对应详细的按键。Vue提供了按键修饰符：
```
<input v-on:keyup.enter="submit">//当按键为enter时，调用submit方法
```
3. sync修饰符
有时候需要在父子组件中，更新某属性的值，使用.sync修饰符可以当属性变化时，只更新父组件的属性。

    例如：[demo](https://codesandbox.io/s/inspiring-villani-o7l5s2?file=/src/App.vue)