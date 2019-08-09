# Vue.js Day01
+ Vue.js 的引入方式
```html
    <!-- 1. 外引方式 通过 使用URL的方式 -->
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script>
    <!-- 2. 本地文件的方式引入 -->
    <script src="./lib/vue.js"></script>
```

## Vue.js 代码结构

```js
// 2.创建 Vue 实例对象
    var vm = new Vue({
        el: '#app', // 选择器的名称 表示 当前new的vue实例，要控制页面上的哪一个区域
        data: { // 存放el 中要用到的数据
            msg: '欢迎学习Vue' // 指令
        }
    })
```

### Vue.js 指令
### 什么是指令

### 指令的学习

#### `v-cloak` 指令

> 案例:
> 01-v-cloak的学习.html
```html
    <div id="app">
        <!-- 插值 {{ }} 会因为加载顺序的问题造成 闪烁问题
        1.通过使用 v-cloak 来解决
        -->
        <h3 v-cloak>{{ msg }}</h3>
        <!-- 2. 使用 v-text 也可以解决 闪烁问题 -->
        <h2 v-text="msg"></h2>

        <!-- 插值{{}}表达式和v-text区别 -->
        <p>++++++++ {{ msg }} +++++++++</p>
        <p v-text="msg">==============</p>
        <!-- v-text 默认是没有闪烁问题
        v-text 会覆盖元素中原本的内容，但是插值表达式只会替换
        自己的这个占位符，不会把整个元素的内容情况
        -->

    </div>
```
```js
    var vm = new Vue({
        el: '#app',
        data: {
            msg: 'v-cloak是用来解决常见的一个问题'
        }
    })
```

#### `v-text` 和 `v-html`

#### `v-bind` 指令
1\. 在vue中，v-bind是用来绑定属性的指令
使用 **v-bind** 有3种方式：
+ 直接使用v-bind指令

+ 使用简化指令 

+ 拼接绑定内容

```html
    <div id="app">
        <input type="button" value="按钮" title="mytitle2222">
        
        <!-- 1.动态绑定属性 -->
        <input type="button" value="按钮2" v-bind:title="mytitle">
        <!-- 2.简化指令 v-bind:属性  =  :属性 -->
        <input type="button" value="按钮2" :title="mytitle">
        <!-- 3.拼接表达式（合法JS表达式）格式化 -->
        <input type="button" value="按钮2" :title="mytitle + '123'">
    </div>
```
```js
    var vm = new Vue({
        el: '#app',
        data: {
            mytitle: '这是一个自定义的title'
        }
    })
```
#### `v-on` 指令
> Vue中提供`v-on`事件绑定机制

```html
    <div id="app">
        <input type="button" value="按钮" title="mytitle2222">
        
        <!-- 1.动态绑定属性 -->
        <input type="button" value="按钮2" v-bind:title="mytitle">
        <!-- 2.简化指令 v-bind:属性  =  :属性 -->
        <input type="button" value="按钮2" :title="mytitle">
        <!-- 3.拼接表达式（合法JS表达式）格式化 -->
        <input type="button" value="按钮2" :title="mytitle + '123'">
    </div>
```
```js
    function clickHandler() {
        
    }
    var vm = new Vue({
        el: '#app',
        data: {

        },
        methods: {
            sayHello: function () {
                alert('hello')
            }
        },
    })
```

### 跑马灯案例

### 事件修饰符

### `v-model` 事件修饰符

### `v-for` 遍历
#### 4种使用方式

#### `key` 


