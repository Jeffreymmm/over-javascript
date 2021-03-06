## 一 vue 简介

### 1.0 体验原生 DOM 编程与 MVVM 编程区别

原生 DOM 编程：

```html
<div class="div"></div>

<script>
  let div = document.querySelector(".div");

  let arr = ["1", "2", "3"];

  let insertStr = "";
  for (let i = 0; i < arr.length; i++) {
    insertStr += "<div>" + arr[i] + "</div>";
  }

  div.innerHTML = insertStr;
</script>
```

Vue 中的写法：

```html
<div class="div">
  <div v-for="item in arr">{{item}}</div>
</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: ".div",
    data: {
      arr: ["1", "2", "3"],
    },
  });
</script>
```

上面的两个示例代码作用一致，是前端开发中最常见的 DOM 界面修改操作，但是在 Vue 的代码中，更加直观、形象，避免了 JS 中直接对 DOM 的操作,只用简单的修改 data 原数据，就能实现界面数据的变化。

### 1.1 MVVM

MVVM 是前端视图层的分层开发思想，将前端视图的结构划分为 M（model）、V（view）、VM（view-model）三层：

- M：数据模型层，这里是接口请求到的数据结果集，封装于 data 对象中，专门用来保存每个页面里单独的数据。
- V：视图层，vue 实例所控制的元素区域，即每个页面的 html 结构。
- VM：VM 调度者，即 new 出来的 vue 实例对象，用来解耦视图层与数据模型层。视图层想要获取或保存数据的都需要由 vm 做中间处理。

贴士：

- MVC 里的 M 是指数据库里面的数据，MVVM 里的 M 是指页里面的数据（data 里的数据）
- MVC 里的 C 是控制器，由不同的控制函数/对象，手动实现调度数据与视图转换，MVVM 里 VM 是自动进行数据与模型关系驱动的。

### 1.2 Vue 简介

Vue 是一个渐进式 MVVM 框架，只关注视图层（view），用来构建 Web 应用界面。所谓渐进式，即我们需要哪些功能就使用框架的哪些模块即可，vue 这样处理使其减少侵入性。

Vue 提供的主要功能：

- 声明式渲染：Vue 的核心库提供了数据渲染功能（vue 模板引擎），实现视图与数据解耦。
- 组件系统：对界面进行组件化
- 前端路由：可以用来制作移动端单页面应用
- 状态管理：对共享数据进行管理

Vue 的核心特点：

- 数据绑定：MVVM 框架的核心特点。当数据发生改变，自动更新视图，底层基于 Object.definedProperty 中的 setter/getter 代理数据，监控对数据的操作。（由于该属性 IE8 不兼容，所以 vue 只支持 IE9 以上版本）
- 组合的视图组件：ui 页面可以映射为组件数，这些组件具备可维护、可重用、可调试性。
- 虚拟 DOM：在内存中生成与真实 DOM 对应的数据结构，即虚拟 DOM，当数据发生变化时，通过虚拟 DOM，计算出重新渲染组件所需要的最小资源，并应用到真实 DOM 上。

贴士：在操作大量 DOM 时，js 的运行速度会被严重拖累。时常在更新数据后需要重新渲染页面，这样会造成一个困扰：数据未发生改变的地方也要被重新渲染一遍，资源严重浪费，虚拟 DOM 很好的解决了该问题。

## 二 HelloWorld

### 1.1 HelloWorld 示例

```html
<div id="app">
  <div>{{msg}}</div>
  <!-- 获取数据 -->
  <button v-on:click="change">点击弹出数据</button>
  <!-- 绑定事件 -->
</div>

<!-- 当导入vue之后，在浏览器的内存中就多了一个vue构造函数 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  new Vue({
    // Vue实例
    el: "#app", // 挂载元素
    data: {
      // 数据源
      msg: "hello world",
    },
    methods: {
      change() {
        alert(this.msg);
      },
    },
  });
</script>
```

### 1.2 示例介绍

每一个应用都是通过 Vue 这个构造函数来创建根实例来启动的：

```js
    let app = new Vue({
        选项对象1,
        选项对象2,
        ...
    })
```

传入的选项对象包含：挂载元素、数据、模板、方法等，如下所示最常见的三个选项对象：

- el：挂载点，可以是元素，也可以是 CSS 选择器，支持原生 JS 写法
- data：代理数据
- methods：定义方法

Vue 代理 data 数据在 HTML 中使用插值 `{{}}` 进行渲染，除了绑定属性外，可以使用 js 表达式进行简单的运算，以及使用三元运算符，但不支持语句与流程控制。如果要真的输出 {{}} 此时可以使用 v-pre 指令：`<div v-pre>{{hi}}</div>`。

每个 Vue 实例都会代理其对应 data 对象中的所有属性：

```html
<div class="div">渲染数据为：{{a}}</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<script>
  let result = {
    a: 1,
  };

  let app = new Vue({
    el: ".div",
    data: {
      a: 1,
    },
  });

  console.log("app.a = ", app.a); // 1
  console.log("app._data.a = ", app._data.a); // 1

  // 修改代理数据中的值，不会修改原始数据的值
  app.a = 2;
  console.log("修改代理数据为2，原始数据值为：", result.a); // 1

  // 修改原始数据中的值，也不会再修改代理数据中的值
  result.a = 3;
  console.log("修改原始数据为3，代理数据为：", app.a); // 2
</script>
```
