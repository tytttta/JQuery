# 一 JQuery遍历
## 1.1 什么是遍历
Query 遍历用于根据其相对于其他元素的关系来"查找"（或选取）HTML 元素。以某项选择开始，并沿着这个选择移动，直到抵达您期望的元素为止。

下图展示了一个家族树。通过 jQuery 遍历，您能够从被选（当前的）元素开始，轻松地在家族树中向上移动（祖先），向下移动（子孙），水平移动（同胞）。
这种移动被称为对 DOM 进行遍历。

![结构图](https://github.com/tytttta/JQuery/blob/master/juery_travel.png)

图示解析：
* \<div> 元素是 \<ul> 的父元素，同时是其中所有内容的祖先。
* \<ul> 元素是 \<li> 元素的父元素，同时是 \<div> 的子元素
* 左边的 \<li> 元素是 <span> 的父元素，\<ul> 的子元素，同时是 \<div> 的后代。
* \<span> 元素是 \<li> 的子元素，同时是 \<ul> 和\<div> 的后代。
* 两个 \<li> 元素是同胞（拥有相同的父元素）。
* 右边的 \<li> 元素是 \<b> 的父元素，\<ul> 的子元素，同时是 \<div> 的后代。
* \<b> 元素是右边的 \<li> 的子元素，同时是 \<ul> 和 \<div> 的后代。

# 二 jQuery遍历-祖先
祖先是父、祖父或曾祖父等等。

通过 jQuery，您能够向上遍历 DOM 树，以查找元素的祖先。

## 2.1 向上遍历 DOM 树
这些 jQuery 方法很有用，它们用于向上遍历 DOM 树：
* parent()
* parents()
* parentsUntil()

## 2.2 jQuery parent() 方法
parent() 方法返回被选元素的直接父元素。 该方法只会向上一级对 DOM 树进行遍历。

下面的例子返回每个 \<span> 元素的的直接父元素：
````
$(document).ready(function(){
   $("span").parent().css({"color":"red","border":"2px solid red"});
});
<p>p (父元素)
        <span>span</span>
      </p> 
````

## 2.3 jQuery parents() 方法
parents() 方法返回被选元素的所有祖先元素，它一路向上直到文档的根元素 (\<html>)。

下面的例子返回所有 \<span> 元素的所有祖先：
````
$(document).ready(function(){
  $("span").parents();
});
````
## 2.4 Query parentsUntil() 方法
parentsUntil() 方法返回介于两个给定元素之间的所有祖先元素。

下面的例子返回介于 <span> 与 <div> 元素之间的所有祖先元素：
````
$(document).ready(function(){
  $("span").parentsUntil("div");
});
````

# 三 jQuery 遍历 - 后代

## 3.1 向下遍历 DOM 树
下面是两个用于向下遍历 DOM 树的 jQuery 方法：
* children()
* find()

## 3.2 jQuery children() 方法
children() 方法返回被选元素的所有直接子元素。 该方法只会向下一级对 DOM 树进行遍历。

下面的例子返回每个 \<div> 元素的所有直接子元素：
````
$(document).ready(function(){
  $("div").children();
});
````
您也可以使用可选参数来过滤对子元素的搜索。

下面的例子返回类名为 "1" 的所有 \<p> 元素，并且它们是\<div> 的直接子元素：
````
$(document).ready(function(){
  $("div").children("p.1");
});
````

## 3.3 jQuery find() 方法
find() 方法返回被选元素的后代元素，一路向下直到最后一个后代。 下面的例子返回属于 \<div> 后代的所有 \<span> 元素：
````
$(document).ready(function(){
  $("div").find("span");
});
````
下面的例子返回 \<div> 的所有后代：
````
$(document).ready(function(){
  $("div").find("*");
});
````

# 四 jQuery 遍历 - 同胞
同胞拥有相同的父元素。 通过 jQuery，您能够在 DOM 树中遍历元素的同胞元素。

## 4.1 在 DOM 树中水平遍历
有许多有用的方法让我们在 DOM 树进行水平遍历：
* siblings()
* next()
* nextAll()
* nextUntil()
* prev()
* prevAll()
* prevUntil()

## 4.2 jQuery siblings() 方法
siblings() 方法返回被选元素的所有同胞元素。

下面的例子返回 \<h2> 的所有同胞元素：
````
$(document).ready(function(){
  $("h2").siblings();
});
````
您也可以使用可选参数来过滤对同胞元素的搜索。

下面的例子返回属于 \<h2> 的同胞元素的所有 \<p> 元素：
````
$(document).ready(function(){
  $("h2").siblings("p");
});
````
## 4.3 jQuery next() 方法
next() 方法返回被选元素的下一个同胞元素。 **该方法只返回一个元素。**

下面的例子返回 \<h2> 的下一个同胞元素：
````
$(document).ready(function(){
  $("h2").next();
});
````
## 4.4 jQuery nextAll() 方法
nextAll() 方法返回被选元素的所有跟随的同胞元素。

下面的例子返回 \<h2> 的所有跟随的同胞元素：
````
$(document).ready(function(){
  $("h2").nextAll();
});
````

## 4.5 jQuery nextUntil() 方法
nextUntil() 方法返回介于两个给定参数之间的所有跟随的同胞元素。

下面的例子返回介于 \<h2> 与 \<h6> 元素之间的所有同胞元素：
````
$(document).ready(function(){
  $("h2").nextUntil("h6");
});
````

## 4.6 jQuery prev(), prevAll() & prevUntil() 方法
prev(), prevAll() 以及 prevUntil() 方法的工作方式与上面的方法类似，只不过方向相反而已：
它们返回的是前面的同胞元素（在 DOM 树中沿着同胞之前元素遍历，而不是之后元素遍历）

# 五 jQuery 遍历 - 过滤
## 5.1 缩小搜索元素的范围
三个最基本的过滤方法是：first(), last() 和 eq()，它们允许您基于其在一组元素中的位置来选择一个特定的元素。

其他过滤方法，比如 filter() 和 not() 允许您选取匹配或不匹配某项指定标准的元素。

## 5.1 jQuery first() 方法
first() 方法返回被选元素的首个元素。

下面的例子选取首个 \<div> 元素内部的第一个 \<p> 元素：
````
$(document).ready(function(){
  $("div p").first();
});
````

## 5.2 jQuery last() 方法
last() 方法返回被选元素的最后一个元素。

下面的例子选择最后一个 \<div> 元素中的最后一个 \<p> 元素：
````
$(document).ready(function(){
  $("div p").last();
});
````
## 5.3 jQuery eq() 方法
eq() 方法返回被选元素中带有指定索引号的元素。

索引号从 0 开始，因此首个元素的索引号是 0 而不是 1。下面的例子选取第二个 \<p> 元素（索引号 1）：
````
$(document).ready(function(){
  $("p").eq(1).css("background-color","yellow");
});

<p>菜鸟教程 (index 0).</p>
<p>http://www.runoob.com (index 0/1)。</p> //此处变色
<p>google (index 2).</p>
<p>http://www.google.com (index 3)。</p>
````
## 5.4 jQuery filter() 方法
filter() 方法允许您规定一个标准。不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回。

下面的例子返回带有类名 "url" 的所有 \<p> 元素：
````
$(document).ready(function(){
  $("p").filter(".url");
});
````

## 5.5 jQuery not() 方法
not() 方法返回不匹配标准的所有元素。

提示：not() 方法与 filter() 相反。

下面的例子返回不带有类名 "url" 的所有 \<p> 元素：
````
$(document).ready(function(){
  $("p").not(".url");
});
````
