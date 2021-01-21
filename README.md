# Learning-Vue

*learning materials of Vue*

> 1. Vue基础  
> 2. 本地应用  
> 3. 网络应用  
> 4. 综合应用  

<br>

---

> ## 一、Vue基础   

1. [Vue简介](https://cn.vuejs.org)  
   1. **Javascript**框架  
   2. 简化**Dom**操作  
   3. **响应式**数据驱动  

2. [第一个Vue程序](EXAMPLES/Ex1_firstVue.html)  
   1. 导入**开发版本**的Vue.js  
   2. 创建**Vue**实例对象，设置`el`属性和`data`属性  
      ``` javascript
      var app = new Vue({
          el: "#id",
          data: {
              msg1: "message1",
              msg2: "message2"
          }
      })
      ```
   3. 使用**模板语法**把数据渲染到页面  

3. [`el` 挂载点](EXAMPLES/Ex2_useOfEl.html)  
   **作用**: 设置**Vue**实例挂载\(管理\)的元素  
   1. **Vue**实例的作用范围  
      `el`选项选中的元素及其内部子元素  
   2. 是否可以使用其他的选择器  
      可以使用其他选择器\(推荐使用id\)
   3. 是否可以设置其他的dom元素  
      可以使用**双标签**，但不能使用`html`和`body`标签  

4. [`data` 数据](EXAMPLES/Ex3_useOfData.html)  
   1. **Vue**中用到的数据定义在`data`中  
   2. `data`中可以写**复杂类型**的数据  
   3. 渲染复杂类型数据时遵守js的**语法**即可  

<br>

> ## 二、本地应用  
- 内容绑定，事件绑定 `v-text, v-html, v-on基础`  
- 显示切换，属性绑定 `v-show, v-if, v-bind`  
- 列表循环，表单元素绑定 `v-for, v-on补充, v-model`  

1. **内容绑定，事件绑定**  
   1. [`v-text`](EXAMPLES/Ex4_localApp1.html)  
      - `v-text` **作用**为设置标签的内容\(textContent\)  
      - 默认写法会替换全部内容，使用**差值表达式-{{}}**可以替换指定内容  
      - 内部支持写**表达式**\(如字符串拼接\)  
   2. [`v-html`](EXAMPLES/Ex4_localApp1.html)  
      - `v-html` **作用**为设置标签的`innerHTML`  
      - 内容中有 `html` 结构则会被解析为**标签**  
      - `v-text` 无论内容是什么只会解析为**文本**  
      - 解析文本使用 `v-text`，需要解析**html结构**则使用`v-html`  
   3. [`v-on`](EXAMPLES/Ex4_localApp1.html)  
      - `v-on` **作用**为绑定事件\(click、dblclick等\)  

   **案例**: [计数器](EXAMPLES/Ex4_localAppExample1.html)  

2. **显示切换，属性绑定**  
   1. [`v-show`](EXAMPLES/Ex4_localApp2.html)  
      - `v-show` 的作用是根据**真假**切换元素的显示状态  
      - 原理是修改元素的`display`，实现显示隐藏  
      - 指令后面的内容最终都会被解析为**布尔值**  
      - 值为`true`则元素显示，为`false`则元素隐藏  
      - 数据改变后对应元素的显示状态会**同步更新**  
   2. [`v-if`](EXAMPLES/Ex4_localApp2.html)  
      - `v-if` 的作用是根据表达式的**真假**切换元素的显示状态  
      - 本质是通过操纵**dom**元素来切换显示状态  
      - 表达式的值为`true`则元素**存在**于dom树中，为`false`则从dom树种**移除**  
      - **频繁切换**使用`v-show`，反之使用`v-if`\(前者切换的消耗小\)  
   3. [`v-bind`](EXAMPLES/Ex4_localApp2.html)  
      - `v-bind` 的作用是为元素**绑定属性**  
      - **完整写法**是`v-bind:属性名="属性值"`  
      - **简写**可以直接省略v-bind，写为`:属性名="属性值`  
      - 需要动态的增删class建议使用对象方法`:class={className: isActive}`  

   **案例**: [图片切换](EXAMPLES/Ex4_localAppExample2.html)  

3. **列表循环，表单元素绑定**  
   1. [`v-for`](EXAMPLES/Ex4_localApp3.html)  
      - `v-for` 的作用是根据数据生成列表结构  
      - 数组经常和`v-for`结合使用  
      - 语法是`(item, index) in 数据名`\(变量名item、index可以自己命名，但顺序为`item、index`\)  
      - `item`和`index`可以结合其他指令一起使用  
      - 数组长度的更新会同步到页面上，是响应式的  
   2. [`v-on`补充: 传参、事件修饰符](EXAMPLES/Ex4_localApp3.html)  
      - `v-on:click=func1(参数1, 参数2, ...);  // func1是一个函数`
      - 事件绑定的方法写成**函数调用**的形式，可以传入自定义参数  
      - 定义方法时需要定义**形参**来接收传入的实参  
      - 时间的后面跟上`.`**修饰符**可以对事件进行限制  
      - `.enter`可以限制触发的按键为回车  
      - 事件修饰符有多种  
   3. [`v-model`](EXAMPLES/Ex4_localApp3.html)  
      - `v-model` 的作用是便捷地设置和获取**表单元素**的值  
      - 绑定的数据会和表单元素的**值**相关联\(修改其中任何一个都会使另一个同步更新\)  
      - 绑定的数据 \<\- \- \- \-\> 表单元素的值  

   **案例**: [记事本](EXAMPLES/Ex4_localAppExample3.html)  

<br>

> ## 三、网络应用  

1. `axios` \- 网络请求库  
   ``` javascript
      // 地址和参数用?连接，参数可以多个
      // then里面的两个函数分别为请求成功/失败的回调函数
      axios.get(地址?key=value&key2=value2).then(function(responce){}, function(error){})

      // 地址和参数用,分隔，参数可以多个(用键值对表示)
      // then里面的两个函数分别为请求成功/失败的回调函数
      axios.post(地址, {key: value, key2: value2}).then(function(responce){}, function(error){})
   ```

2. `axios`+`vue`  
   1. `axios`回调函数中的`this`已经改变\(不再表示vue对象\)，无法访问到`vue`对象中的`data`中的值  
   2. 方法: 使用`axios`前先用`that = this`将this保存起来, 回调函数中直接调用`that`  
   3. 和本地应用最大的区别是改变了**数据来源**  


