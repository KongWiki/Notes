## Vue笔记

### 7个属性

- el属性

- - 用来指示vue编译器从什么地方开始解析 vue的语法，可以说是一个占位符。

- data属性

- - 用来组织从view中抽象出来的属性，可以说将视图的数据抽象出来存放在data中。

- template属性

- - 用来设置模板，会替换页面元素，包括占位符。

- methods属性

- - 放置页面中的业务逻辑，js方法一般都放置在methods中

- render属性

- - 创建真正的Virtual Dom

- computed属性

- - 用来计算

- watch属性

- - watch:function(new,old){}
  - 监听data中数据的变化
  - 两个参数，一个返回新值，一个返回旧值，



### 常用方法的基础模板

#### v-if

```html
<div id="app">
    <h1 v-if="type=== 'A'">Yes</h1>
    <h1 v-else>NO</h1>
</div>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            type: "B"
        }
    })
```



#### v-for

```html
<div id="app">
    <li v-for="item in items">
        {{item.message}}
    </li>
</div>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            items: [
                {message: "维坤坤好帅"},
                {message: "维坤坤好好"},
                {message: "维坤坤好牛"},

            ]
        }
    })
```



#### v-on

```html
<div id="app">
    <button v-on:click="sayHi">Click Me</button>
</div>
<script>
    var app = new Vue({
        el: '#app',
        // 数据
        data: {
            message: "维坤坤好帅"
        },
        // 事件
        methods: {
            sayHi: function () {
                alert(this.message)
            }
        }
    })
```



#### v-bind

```html

```



### 表单双绑、组件



### 生命周期

每个Vue实例创建时，都会经历一系列的初始化过程，同时也会调用相应的生命周期钩子，可以利用这些钩子，在合适的时机执行我们的业务逻辑。

* **created** 实例创建完成后调用，此阶段完成了数据的观测等，但是尚未挂载，$el还不可用
* **mounted** el挂载到实例之后调用，一般我们的第一个业务逻辑会在这里开始。
* **beforeDestory** 实例销毁之前调用。主要解绑一些使用addEventListener监听事件等

![](https://raw.githubusercontent.com/KongWiki/cloudImg/master/vue%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.jpg)



### 指令与事件

指令是Vue.js模板中最常用的一项功能，它带有前缀`v-`，指令的主要职责就是当其表达式的值改变时，相应地将某些行为应用到DOM上

* **v-bind** 

  基本用途是动态更新HTML元素上的属性，比如id、class等，其中其可使用提供的语法糖

  ```html
  <a v-bind:href="url">链接</a>
  <!--缩写为-->
  <a :href="url">链接</a>
  ```

* **v-on**

  绑定事件监听器，这样可以做一些交互。

   

* **v-cloak**

  在Vue实例结束编译时从绑定的HTML中移除，经常和CSS中的display:none；配合

  当网速较慢的时候，Vue还未加载完时，会显示模板语言，直到创建Vue实例、编译模板时，DOM才会被替换，会导致屏幕出现闪动。解决办法：

  ```css
  [v-cloak]{
      display: none;
  }
  ```

#### 条件渲染指令

* **v-if, v-else-if, v-else**

  即为逻辑判断，同其他编程语言用法一样

* **v-show** 

  用法与**v-if**基本一致，只不过**v-show**是改变元素的css属性display。当v-show表达式的值为fasle时，元素会隐藏，**v-show** 不能在<template>上使用。

#### 区别对比

​	**v-if** 和**v-show** 具有类似的功能，但是**v-if** 才是真正的条件渲染，它会根据表达式适当的销毁或者重建元素及绑定的事件，若表达式false，则一开始元素/组件并不会被渲染，只有当条件第一次变为真时才开始编译。

​	**v-show** 只是简单的css属性，无论条件真与否，都会被编译。所以**v-show**适用于频繁切换条件，**v-if**适合条件不经常改变的场景。

#### 表单相关指令

* **v-model** 

  表单控制控件显示的值只依赖所绑定的数据，不在关心初始化时的value属性，在对应的控件上插入值也不会响应。



