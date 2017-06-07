Vue.js_Intrduction
===
## 什么是Vue.js?
Vue.js（读音 /vjuː/，类似于 view） 是一套构建用户界面的渐进式框架。与其他重量级框架不同的是，Vue 采用自底向上增量开发的设计。Vue 的核心库只关注视图层，它不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与单文件组件和 Vue 生态系统支持的库结合使用时，Vue 也完全能够为复杂的单页应用程序提供驱动。
***
## Vue.js框架的引用
最简单的方法是直接调用下面网址的js代码。  

```<script src="https://unpkg.com/vue/dist/vue.js"></script>```  
也可以直接下载下来到本地，可离线使用。  
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
### MVVM 数据绑定
MVVM的本质是通过数据绑定链接*View*和*Model*，让数据的变化自动映射为视图的更新。Vue.js在数据绑定的API设计上借鉴了*Angular*的指令机制：用户可以通过具有特殊前缀的HTML 属性来实现数据绑定，也可以使用常见的花括号模板插值，或是在表单元素上使用双向绑定。  
插值本质上也是指令，只是为了方便模板的书写。在模板的编译过程中，Vue.js会为每一处需要动态更新的DOM节点创建一个指令对象。每当一个指令对象观测的数据变化时，它便会对所绑定的目标节点执行相应的DOM操作。基于指令的数据绑定使得具体的DOM操作都被合理地封装在指令定义中，业务代码只需要涉及模板和对数据状态的操作即可，这使得应用的开发效率和可维护性都大大提升。  
![imgage](http://img.ptcms.csdn.net/article/201508/11/55c9abacf113a.jpg)
## 处理用户输入
为了让用户和你的应用进行互动，我们可以用 v-on 指令绑定一个事件监听器，通过它调用我们 Vue 实例中定义的方法：  
```
<!DOCTYPE html>
<html>
<script src="https://unpkg.com/vue/dist/vue.js"></script>
<body>

  <div id="app-5">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">逆转消息</button>
</div>
</body>

<script src="2.js"></script>

</html>
```
```
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: 'Hello Vue.js!'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
```
注意在 reverseMessage 方法中，我们更新了应用的状态，但没有触碰 DOM——所有的 DOM 操作都由 Vue 来处理，你编写的代码只需要关注底层逻辑。  
Vue 还提供了 v-model 指令，它能轻松实现表单输入和应用状态之间的双向绑定。
```
<div id="app-6">
  <p>{{ message }}</p>
  <input v-model="message">
</div>
```
```
var app6 = new Vue({
  el: '#app-6',
  data: {
    message: 'Hello Vue!'
  }
})
```
 ![image](https://github.com/JohnChin/Vue_Intrduction/blob/quote/Input/input1.png)  
## Vue.js的常用指令
上面用到的v-model是Vue.js常用的一个指令，那么指令是什么呢？

Vue.js的指令是以v-开头的，它们作用于HTML元素，指令提供了一些特殊的特性，将指令绑定在元素上时，指令会为绑定的目标元素添加一些特殊的行为，我们可以将指令看作特殊的HTML特性（attribute）。
Vue.js提供了一些常用的内置指令，接下来我们将介绍以下几个内置指令：
* v-if指令
* v-show指令
* v-else指令
* v-for指令
* v-bind指令
* v-on指令  
Vue.js具有良好的扩展性，我们也可以开发一些自定义的指令。
### 组件系统
![image](https://cn.vuejs.org/images/components.png)
## 一个简单的DEMO
接下来，用Vue.js的一些知识，来实现一个简单的签到系统。
