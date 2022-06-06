# Vue2初识
Vue是一门前端语言的框架，主要关注视图层,通过与现代化的工具链以及各种支持类库结合使用时，能够为复杂的单页应用提供驱动。
## Vue的安装
* 直接用CDN引入：
```
//完整版
<script src="https://cdn.bootcdn.net/ajax/libs/vue/2.6.12/vue.js"></script>
//运行时版
<script src="https://cdn.bootcdn.net/ajax/libs/vue/2.6.12/vue.js"></script>
```
* npm或者yarn安装：
```
//安装Vue2
npm install vue@2
yarn add vue@2
```
* 安装Vue-cli官方工具
```
//安装全局Vue2
npm install -g @vue/cli@2
yarn global add @vue/cli@2
```
## Vue版本
Vue有两个版本：分别是完整版vue.js和运行时版vue.runtime.js。同时完整版还有生产环境的vue.min.js，运行时版还有vue.runtime.min.js。完整版比运行时版多包含了编译器，所以也比运行时版体积大40%。
```
// 完整版可以直接在vue文件里写HTML标签
new Vue({
  template:'<div>{{hi}}</div>'
})
// 运行时版需要h函数
new Vue({
  render(h){
    return h('div', this.hi)
  }
})
```
最佳的版本选择方法是选择运行时版，体积小，配合vue-loader编译vue文件，便于开发。
## 使用网站写Vue
可以通过 https://codesandbox.io/ 网站，编写vue代码。
1. 首先点击页面右上角Create Sandbox浅绿色按钮；
2. 点击Vue3，创建一个Vue3项目；
3. 点击中间上方标题更改项目名；
4. 写代码；
5. 点击左上角三横线>File>Export to ZIP,将代码打包保存到本地。




