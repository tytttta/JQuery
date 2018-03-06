# 一 jQuery 简介
## 1.1 学习的基础
* HTML
* CSS 
* Js

## 1.2 什么是jQuery
jQuery是一个轻量级额“写得少，做得多”的js函数库，包括以下功能：
* HTML元素选取
* HTML元素操作
* CSS操作
* HTML事件函数
* js特效和动画
*　HTML DOM遍历和修改
* AJAX
* Utilities

# 二 jQuery 安装
## 2.1 网页中添加jQuery
可以通过多种方法在网页中添加jQuery，如：
* 从jquery.com下载jQuery库
* 从CDN中载入jQuery，如从Google中加载jQuery.

## 2.2 有两个版本的jQuery可以下载：
* Production version-用于实际的网站中，已被精简和压缩
* Development version-用于测试和开发（未压缩，是可读的代码）


jQuery库是一个js文件，可以使用HTML中的<script>标签引用。
````
  <head>
    <script src="jquery-1.1.0.2.min.js></script>
   </head>  
````
   
   将下载的文件放在网页的同一目录下，就可以使用jQuery了。
   
 ## 2.3 替代方案
   如果不希望下载并存放jQuery，可以通过CDN（内容分发网络）引用。
   
   如果你的站点用户是国内的，建议使用百度、又拍云、新浪等国内CDN地址，如果你站点用户是国外的可以使用谷歌和微软。

   注：本站实例均采用菜鸟教程 CDN 库。

   如需从菜鸟教程、又拍云、新浪、谷歌或微软引用 jQuery，请使用以下代码之一：
   
菜鸟教程CDN：
````
   <head>
     <script src="http://cdn.static.runoob.com/libs/jquery/1.10.2/jquery.min.js">
     </script>
   </head>
````

百度CDN:
 ````
 <head>
   <script src="https://apps.bdimg.com/libs/jquery/2.1.4/jquery.min.js">
   </script>
</head>
````

又拍云 CDN:
````
 <head>
   <script src="http://upcdn.b0.upaiyun.com/libs/jquery/jquery-2.0.2.min.js">
   </script>
 </head>
````

新浪 CDN:
 ````
 <head>
  <script src="http://lib.sinaapp.com/js/jquery/2.0.2/jquery-2.0.2.min.js">
  </script>
 </head>
````

Google CDN:
````
 <head>
  <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js">
  </script>
 </head>
````
 
 # 三 jQuery语法
 ## 3.1 jQuery语法
 jQuery语法通过选取HTML元素，并对选取的元素执行某些操作。
 
 基础语法：$(selector).action()
 
 实例：
 * $(this).hide() - 隐藏当前元素
 * $("p").hide() - 隐藏所有的\<p\>元素
 * $("p.test").hide() - 隐藏所有的 class=“test”的\<p\>元素
 * $("#test").hide() - 隐藏所有id="test"的元素
 
 ## 3.2 文档就绪事件
 经常看到一些实例中所有的jQuery函数卫浴 一个document ready函数中：
 ````
 $(document).ready(function(){
     code;
 });
 ````
 这是为了防止文档在完全加载前运行jQuery代码，即在DOM加载完成后才可以对DOM进行操作。如果在文档没有完全加载完前就运行函数，操作可能会失败。
 
 # 四 jQuery选择器
 ## 4.1 jQuery选择器
 jQuery选择器允许对HTML元素组或单个元素进行操作。jQuery选择器基于元素的id，类，类型，属性，属性值等“查找”HTML元素。它基于已经存在的CSS选择器，同时还有一些自定义的选择器。
 
 **jQuery中所有选择器都以美元符号开头：$().**
 
 ## 4.2 元素选择器
 jQuery元素选择器基于元素名选取元素。
 
 实例：点击按钮后所有\<p>元素都隐藏：
 ````
  $(document).ready(function(){
    $("button").click(function(){
      $("p").hide();
    });
  });
 ````
  
 ## 4.3 #id选择器 
 页面中元素的id应该是唯一的，所以在页面中选取唯一元素要通过id选择器。
 
 实例：当用户点击按钮后，有 id="test" 属性的元素将被隐藏：
 ````
 $(document).ready(function(){
   $("button").click(function(){
     $("#test").hide();
   });
 });
 ````
 ## 4.4 .class选择器
 实例：用户点击按钮后所有带有 class="test" 属性的元素都隐藏：
````
$(document).ready(function(){
  $("button").click(function(){
    $(".test").hide();
  });
});
````
## 更多实例：
|语法|描述|
|------|----|
|$("\*")|选取所有的元素|
|$("this")|选取当前HTML元素|
|$("p.into")|选取class为into的\<p\>元素|
|$("p.first")|选取第一个\<p\>元素|
|$("ul li:first")|选取第一个\<ul\>元素的第一个\<li>元素|
|$("ul li:first-child")|选取每个 \<ul> 元素的第一个\<li> 元素|
|$("[href]")|选取带有 href 属性的元素|
|$("a[target='_blank']")|选取所有 target 属性值等于 "_blank" 的\<a> 元素|
|$("a[target!='_blank']")|选取所有 target 属性值不等于 "_blank" 的 \<a> 元素|
|$(":button")|选取所有 type="button" 的\<input> 元素 和 \<button> 元素|
|$("tr:even")|选取偶数位置的 \<tr> 元素|
|$("tr:odd")|选取奇数位置的 \<tr> 元素|
 
   
## 4.5 独立文件中使用jQuery函数
如果网站包含许多页面，并且希望jQuery函数易于维护，那么可以将jQuery函数放到独立的js文件中。
````
<head>
<script src="http://cdn.static.runoob.com/libs/jquery/1.10.2/jquery.min.js">
</script>
<script src="my_jquery_functions.js"></script>
</head>
````

# 五 jQuery事件
## 5.1 什么是事件
页面对不同访问者的响应叫做事件。事件处理程序指的是当HTML中发生某些事件所调用的方法。

## 5.2 jQuery事件方法语法
在jQuery中，大多数DOM事件都有一个等效的jQuery方法。
````
$("p").click(function(){
    code;
});
````

## 5.3常用的jQuery事件方法

- **$(document).ready():** 允许我们在文档完全加载完后执行函数。

- **click():** 当按钮被点击时触发。

实例：当点击事件在某个 \<p> 元素上触发时，隐藏当前的 \<p> 元素：
````
$("p").click(function(){
  $(this).hide();
});
````

- **dblclick():** 当双击元素时，会发生 dblclick 事件。

dblclick() 方法触发 dblclick 事件，或规定当发生 dblclick 事件时运行的函数：
````
$("p").dblclick(function(){
  $(this).hide();
});
````

- **mouseenter():** 当鼠标指针穿过元素时，会发生 mouseenter 事件。

mouseenter() 方法触发 mouseenter 事件，或规定当发生 mouseenter 事件时运行的函数：
````
$("#p1").mouseenter(function(){
    alert('您的鼠标移到了 id="p1" 的元素上!');
});
````

- **mouseleave()**: 当鼠标指针离开元素时，会发生 mouseleave 事件。

mouseleave() 方法触发 mouseleave 事件，或规定当发生 mouseleave 事件时运行的函数：
````
$("#p1").mouseleave(function(){
    alert("再见，您的鼠标离开了该段落。");
});
````
- **mousedown():** 当鼠标指针移动到元素上方，并按下鼠标按键时，会发生 mousedown 事件。

mousedown() 方法触发 mousedown 事件，或规定当发生 mousedown 事件时运行的函数：
````
$("#p1").mousedown(function(){
    alert("鼠标在该段落上按下！");
});
````

- **mouseup():** 当在元素上松开鼠标按钮时，会发生 mouseup 事件。

mouseup() 方法触发 mouseup 事件，或规定当发生 mouseup 事件时运行的函数：
````
$("#p1").mouseup(function(){
    alert("鼠标在段落上松开。");
});
````

- **hover()**: hover()方法用于模拟光标悬停事件。

当鼠标移动到元素上时，会触发指定的第一个函数(mouseenter);当鼠标移出这个元素时，会触发指定的第二个函数(mouseleave)。
````
$("#p1").hover(
    function(){
        alert("你进入了 p1!");
    },
    function(){
        alert("拜拜! 现在你离开了 p1!");
    }
);
````

- **focus():** 当元素获得焦点时，发生 focus 事件。

当通过鼠标点击选中元素或通过 tab 键定位到元素时，该元素就会获得焦点。

focus() 方法触发 focus 事件，或规定当发生 focus 事件时运行的函数：
````
$("input").focus(function(){
  $(this).css("background-color","#cccccc");
});
````

- **blur():** 当元素失去焦点时，发生 blur 事件。

blur() 方法触发 blur 事件，或规定当发生 blur 事件时运行的函数：
````
$("input").blur(function(){
  $(this).css("background-color","#ffffff");
});
````
