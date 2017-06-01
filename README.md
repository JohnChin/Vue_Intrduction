Vue.js_Intrduction
===
## 什么是Vue.js?
Vue.js（读音 /vjuː/，类似于 view） 是一套构建用户界面的渐进式框架。与其他重量级框架不同的是，Vue 采用自底向上增量开发的设计。Vue 的核心库只关注视图层，它不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与单文件组件和 Vue 生态系统支持的库结合使用时，Vue 也完全能够为复杂的单页应用程序提供驱动。
***
## Vue.js框架的引用
最简单的方法是直接调用下面网址的js代码。  

```<script src="https://unpkg.com/vue/dist/vue.js"></script>```  

将这段代码放到html文件中，我们就可以使用关于Vue.js框架了。
## 用Vue.js写第一个Hello World程序
### 声明式渲染
Vue.js 的核心是一个允许采用简洁的模板语法来声明式的将数据渲染进 DOM  
html文件  
```
<!DOCTYPE html>
<html>
<script src="https://unpkg.com/vue/dist/vue.js"></script>

<body>

  <div id="app">
    {{ message }}
  </div>
</body>

<script src="1.js"></script>

</html>
```
js文件
``` 
var app = new Vue({
   el: '#app',
   data: {
    message: 'Hello World!'
   }
 }) 
 ```
 ![image](https://github.com/JohnChin/Vue_Intrduction/blob/quote/quote/result.png)  
Vue 在背后做了大量工作,现在数据和 DOM 已经被绑定在一起，所有的元素都是响应式的。打开你的浏览器的控制台（就在这个页面打开），并修改 app.message，你将看到上例相应的更新。
