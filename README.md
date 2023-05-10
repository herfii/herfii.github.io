# 数字历史实验——技术实现



## 一、 目标效果

<img src="images\image-20220505192049629.png" alt="image-20220505192049629" />

[demo.mp4](demo.mp4)



## 二、网页设计基础

### 2.1 HTML

#### 2.1.1 HTML简介

HTML 是用来描述网页的一种语言。

- HTML 指的是超文本标记语言：**H**yper **T**ext **M**arkup **L**anguage

- HTML 不是一种编程语言，而是一种标记语言

- 标记语言是一套标记标签 (markup tag)

- HTML 使用标记标签来描述网页

  HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

  - HTML 标签是由尖括号包围的关键词

  - HTML 标签通常是**成对出现**的

  - 标签对中的第一个标签是开始标签，第二个标签是结束标签

  - 开始和结束标签也被称为开放标签和闭合标签

    **<标签>内容</标签>**

- HTML 文档包含了HTML 标签及文本内容

- HTML文档也叫做 Web 页面



#### 2.1.2 HTML的页面结构：

![image-20220505190446560](images\image-20220505190446560.png)

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>菜鸟教程(runoob.com)</title>
</head>
<body>
	<h1>我的第一个标题</h1>
	<p>我的第一个段落。</p>
</body>
</html>
```



#### 2.1.3 常见的HTML标签

##### (1) HTML 标题

HTML 标题（Heading）是通过\<h1> - \<h6> 标签来定义的。

```html
<h1>这是一个标题</h1>
<h2>这是一个标题</h2>
<h3>这是一个标题</h3>
```

<h1>这是一个标题</h1>
<h2>这是一个标题</h2>
<h3>这是一个标题</h3>



##### (2) HTML 段落

HTML 段落是通过标签 \<p> 来定义的。

```html
<p>这是一个段落。</p>
<p>这是另外一个段落。</p>
```

<p>这是一个段落。</p>
<p>这是另外一个段落。</p>



##### (3) HTML 链接

HTML 链接是通过标签 \<a> 来定义的。

```html
<a href="https://www.baidu.com">这是一个链接</a>
```

<a href="https://www.baidu.com">这是一个链接</a>



##### (4) HTML 图像

HTML 图像是通过标签 \<img> 来定义的。

```html
<img src="Icon.png" />
```

<img src="Icon.png" />

##### (5) HTML \<div> 标签

\<div> 定义了 HTML 文档中的一个区域部分，浏览器会在其前后显示换行。

\<div> 没有特定的含义，常与 CSS 一同使用，对大的内容块设置样式属性。

\<div> 的另一个常见的用途是页面布局。

```html
<p>这是一些文本。</p>
<div style="color:blue">
<h3>这是一个在 div 元素中的标题。</h3>
<p>这是一个在 div 元素中的文本。</p>
</div>
<p>这是一些文本。</p>
```

<p>这是一些文本。</p>
<div style="color:blue">
<h3>这是一个在 div 元素中的标题。</h3>
<p>这是一个在 div 元素中的文本。</p>
</div>
<p>这是一些文本。</p>



##### (6) HTML \<span> 标签

\<span> 主要用作文本的容器，可以用于对文档中的行内元素进行组合。

\<span> 也没有特定的含义，常与 CSS 一同使用时，\<span> 可用于为部分文本设置样式属性。

```html
<p>我有一件<span style="color:blue">蓝色</span>的衣服。</p>
```

<p>我有一件<span style="color:blue">蓝色</span>的衣服。</p>



##### (7) HTML \<script> 标签

\<script> 用于定义客户端脚本，比如 JavaScript。

\<script> 既可包含脚本语句，也可通过 src 属性引用外部脚本文件。

```html
<script>
    //JavaScript代码
</script>
```

```html
<script type="text/javascript" src="http://api.map.baidu.com/library/CurveLine/1.5/src/CurveLine.min.js">
```



### 2.2 CSS

#### 2.2.1 CSS简介

- CSS 指层叠样式表 (**C**ascading **S**tyle **S**heets)

- CSS定义了HTML 元素的样式，决定了**如何显示**HTML元素

- 当读到一个样式表时，浏览器会根据它来格式化 HTML 文档

- 插入样式表的方法通常有三种:

  - 外部样式表(External style sheet)

    当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，可以通过改变一个文件来改变整个站点的外观。每个页面使用 \<link> 标签链接到样式表。 \<link> 标签在（文档的）头部，如：

    ```html
    <head>
        <link rel="stylesheet" type="text/css" href="mystyle.css">
    </head>
    ```

  - 内部样式表(Internal style sheet)

    当单个文档需要特殊的样式时，就应该使用内部样式表。可以使用 \<style> 标签在文档头部定义内部样式表，如：

    ```html
    <head>
        <style>
            //样式表
        </style>
    </head>
    ```

  - 内联样式(Inline style)

    当样式仅需要在一个元素上应用一次时，可以使用内联样式。内联样式将HTML元素的表现和内容混杂在一起，需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性，如：

    ```html
    <p style="color:blue;">这是一个段落。</p>
    ```

    <p style="color:blue;">这是一个段落。</p>



#### 2.2.2 CSS 语法

CSS 规则由两个主要的部分构成：选择器，以及一条或多条声明:

![img](https://www.runoob.com/wp-content/uploads/2013/07/632877C9-2462-41D6-BD0E-F7317E4C42AC.jpg)

选择器通常是需要改变样式的 HTML 元素。

每条声明由一个属性和一个值组成。

属性（property）是希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。

CSS声明总是以分号 ; 结束，声明总以大括号 {} 括起来：

```css
p {
    color:red;
    text-align:center;
}
```
[example](https://www.runoob.com/try/try.php?filename=trycss_syntax1)



#### 2.2.3 CSS id 和 class 选择器

如果要在HTML元素中设置CSS样式，需要在元素中设置"id" 和 "class"选择器。

##### (1) id 选择器

id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。

HTML元素以id属性来设置id选择器，CSS 中 id 选择器以 "#" 来定义。

以下的样式规则应用于元素属性 id="para1"：

```css
#para1 {
    text-align:center;
    color:red;
}
```
[example](https://www.runoob.com/try/try.php?filename=trycss_syntax_id)



##### (2) class选择器

class 选择器用于描述一组元素的样式，class 选择器有别于id选择器，class可以在多个元素中使用。

class 选择器在HTML中以class属性表示，在 CSS 中，类选择器以一个点"."号显示。

在以下实例中，所有拥有 center 类的 HTML 元素均为居中。

```css
.center {
    text-align:center;
}
```
[example](https://www.runoob.com/try/try.php?filename=trycss_syntax_class)

也可以指定特定的HTML元素使用class。

在以下实例中，所有的 p 元素使用 class="center" 让该元素的文本居中：

```css
p.center {
    text-align:center;
}
```
[example](https://www.runoob.com/try/try.php?filename=trycss_syntax_element_class)



#### 2.2.4 CSS 盒子模型

所有HTML元素可以看作盒子，在CSS中，"box model"这一术语是用来设计和布局时使用。

CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。

盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。

下面的图片说明了盒子模型(Box Model)：

![image-20220505215014146](images\image-20220505215014146.png)

- **Margin(外边距)** - 清除边框外的区域，外边距是透明的。
- **Border(边框)** - 围绕在内边距和内容外的边框。
- **Padding(内边距)** - 清除内容周围的区域，内边距是透明的。
- **Content(内容)** - 盒子的内容，显示文本和图像。
- **width和height（元素的宽度和高度）** - 内容区域（content）的宽度和高度。



### 2.3 JavaScript

#### 2.3.1 JavaScript 简介

JavaScript 是互联网上最流行的脚本语言，这门语言可用于 HTML 和 Web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备。

- JavaScript 是脚本语言。
- JavaScript 是一种轻量级的编程语言。
- JavaScript 是可插入 HTML 页面的编程代码。
- JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。



#### 2.3.2 JavaScript 数据类型

JavaScript 有多种数据类型：数字，字符串，数组，对象等等：

```javascript
var length = 16;                                 // Number 通过数字字面量赋值
var points = x * 10;                             // Number 通过表达式字面量赋值
var lastName = "Johnson";                        // String 通过字符串字面量赋值
var cars = ["Saab", "Volvo", "BMW"];             // Array 通过数组字面量赋值
var person = {firstName:"John", lastName:"Doe"}; // Object 通过对象字面量赋值
```


#### 2.3.3 JavaScript 函数

JavaScript 语句可以写在函数内，函数可以重复引用。

引用一个函数 = 调用函数(执行函数内的语句)。

```javascript
function myFunction(a, b) {
    return a * b;                // 返回 a 乘以 b 的结果
}
```
下面的函数在按钮被点击时会提示 "Welcome Harry Potter, the Wizard"：

```html
<p>点击这个按钮，来调用带参数的函数。</p>
<button onclick="myFunction('Harry Potter','Wizard')">点击这里</button>
<script>
    function myFunction(name, job) {
        alert("Welcome " + name + ", the " + job);
    }
</script>
```

[example](https://www.runoob.com/try/try.php?filename=tryjs_function2)



#### 2.4.4 JavaScript this 关键字

面向对象语言中 this 表示当前对象的一个引用。

但在 JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变。

- 在方法中，this 表示该方法所属的对象。

  在下面的实例中，this 表示 person 对象，因为fullName 方法所属的对象就是 person:

  ```javascript
  var person = {
      firstName: "John",
      lastName : "Doe",
      id       : 5566,
      fullName : function() {
          return this.firstName + " " + this.lastName;
      }
  };
  ```

- 如果单独使用，this 表示全局对象。

  在浏览器中，Window 就是该全局对象为 [**object Window**]：

  ```javascript
  var x = this;
  ```

- 在函数中，this 表示全局对象。

  在函数中，函数的所属者默认绑定到 this 上。在浏览器中，Window 就是该全局对象为 [**object Window**]：

  ```javascript
  function myFunction() {
      return this;
  }
  ```

- 在事件中，this 表示接收事件的元素。

  ```html
  <button onclick="this.style.display='none'">
      点我后我就消失了
  </button>
  ```
  [example](https://www.runoob.com/try/try.php?filename=tryjs_this_event)
  
  

## 三、地图原理与应用

### 3.1 使用场景

地图的使用场景非常广泛。地图定位可以更直观的说明位置及周边环境，让用户更好的了解地理位置信息更好的规划路径，以方便出行。地图实现了定位、导航等互联网上最常见的功能之一。

例如：

<img src="images\image-20220506131450489.png" alt="image-20220506131450489"  />

地图是一种很常见的技术，公司地址，房产位置，饭店，酒店等行业，只要是用户需要找地方的时候，就可能出现地图技术的身影，涉及到我们生活的方方面面。

- 定位
- 地图
- 轨迹
- 路线规划
- 导航
- 路况



### 3.2 技术介绍

常见的地图API有很多，例如：

[高德地图API](https://lbs.amap.com/)

[百度地图API](https://lbsyun.baidu.com/)

[腾讯地图API](https://lbs.qq.com/)

[（地图API合集）](https://github.com/lhywell/map)

其中最常用的是高德地图API（阿里）和百度地图API。



### 3.3 百度地图的使用

API地址：https://lbsyun.baidu.com/



### 3.4 简易demo的实现

[demo.html](demo.html)

