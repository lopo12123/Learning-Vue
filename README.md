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
      - 解析文本使用 `v-text`，需要解析**html结构**则使用 `v-html`  
   3. [`v-on`](EXAMPLES/Ex4_localApp1.html)  
      - `v-on` **作用**为绑定事件\(click、dblclick等\)  

   **案例**: [计数器](EXAMPLES/Ex4_localAppExample1.html)  

2. **显示切换，属性绑定**  
   1. [`v-show`](EXAMPLES/Ex4_localApp2.html)  
   2. [`v-if`](EXAMPLES/Ex4_localApp2.html)  
   3. [`v-bind`](EXAMPLES/Ex4_localApp2.html)  



3. **列表循环，表单元素绑定**

<br>

> ## 三、网络应用  



<br>

> ## 四、综合应用  


