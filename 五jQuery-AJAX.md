# 一 jQuery-AJAX简介
AJAX 是与服务器交换数据的技术，它在不重载全部页面的情况下，实现了对部分网页的更新。

## 1.1 什么是 AJAX？
AJAX = 异步 JavaScript 和 XML（Asynchronous JavaScript and XML）。

简短地说，在不重载整个网页的情况下，AJAX 通过后台加载数据，并在网页上进行显示。

使用 AJAX 的应用程序案例：谷歌地图、腾讯微博、优酷视频、人人网等等。

## 1.2 关于 jQuery 与 AJAX
jQuery 提供多个与 AJAX 有关的方法。

通过 jQuery AJAX 方法，您能够使用 HTTP Get 和 HTTP Post 从远程服务器上
请求文本、HTML、XML 或 JSON - 同时您能够把这些外部数据直接载入网页的被选元素中。

## 二 jQuery - AJAX load() 方法

## 2.1 jQuery load() 方法
jQuery load() 方法是简单但强大的 AJAX 方法。

load() 方法从服务器加载数据，并把返回的数据放入被选元素中。

语法:
````
$(selector).load(URL,data,callback);
````
必需的 URL 参数规定您希望加载的 URL。 可选的 data 参数规定与请求一同发送的查询字符串键/值对集合。
可选的 callback 参数是 load() 方法完成后所执行的函数名称。

这是示例文件（"demo_test.txt"）的内容：
````
<h2>jQuery AJAX 是个非常棒的功能！</h2>
<p id="p1">这是段落的一些文本。</p>
````
下面的例子会把文件 "demo_test.txt" 的内容加载到指定的 <div> 元素中：
````
$(document).ready(function(){
	$("button").click(function(){
		$("#div1").load("/try/ajax/demo_test.txt");
	});
});
<div id="div1"><h2>使用 jQuery AJAX 修改文本内容</h2></div>
<button>获取外部内容</button>
````
也可以把 jQuery 选择器添加到 URL 参数。

下面的例子把 "demo_test.txt" 文件中 id="p1" 的元素的内容，加载到指定的 <div> 元素中：
````
$(document).ready(function(){
  $("button").click(function(){
    $("#div1").load("/try/ajax/demo_test.txt #p1");
  });
});
<div id="div1"><h2>使用 jQuery AJAX 修改文本</h2></div>
<button>获取外部文本</button>
````

# 三 jQuery - AJAX get() 和 post() 方法
jQuery get() 和 post() 方法用于通过 HTTP GET 或 POST 请求从服务器请求数据。

## 3.1 HTTP 请求：GET vs. POST
两种在客户端和服务器端进行请求-响应的常用方法是：GET 和 POST。

* GET - 从指定的资源请求数据
* POST - 向指定的资源提交要处理的数据

GET 基本上用于从服务器获得（取回）数据。注释：GET 方法可能返回缓存数据。

POST 也可用于从服务器获取数据。不过，POST 方法不会缓存数据，并且常用于连同请求一起发送数据。

## 3.2 jQuery $.get() 方法
$.get() 方法通过 HTTP GET 请求从服务器上请求数据。

语法：
````
$.get(URL,callback);
````
必需的 URL 参数规定您希望请求的 URL。
可选的 callback 参数是请求成功后所执行的函数名。

下面的例子使用 $.get() 方法从服务器上的一个文件中取回数据：
````
$("button").click(function(){
  $.get("demo_test.php",function(data,status){
    alert("数据: " + data + "\n状态: " + status);
  });
});
````
$.get() 的第一个参数是我们希望请求的 URL（"demo_test.php"）。

第二个参数是回调函数。第一个回调参数存有被请求页面的内容，第二个回调参数存有请求的状态。

**提示： 这个 PHP 文件 ("demo_test.php") 类似这样：**
demo_test.php 文件代码:
````
<?php
echo '这是个从PHP文件中读取的数据。';
?>
````

## 3.3 jQuery $.post() 方法
$.post() 方法通过 HTTP POST 请求从服务器上请求数据。

语法:
````
$.post(URL,data,callback);
````
必需的 URL 参数规定您希望请求的 URL。可选的 data 参数规定连同请求发送的数据。
可选的 callback 参数是请求成功后所执行的函数名。

下面的例子使用 $.post() 连同请求一起发送数据：
````
$("button").click(function(){
    $.post("/try/ajax/demo_test_post.php",
    {
        name:"菜鸟教程",
        url:"http://www.runoob.com"
    },
        function(data,status){
        alert("数据: \n" + data + "\n状态: " + status);
    });
});
````
$.post() 的第一个参数是我们希望请求的 URL ("demo_test_post.php")。 然后我们连同请求（name 和 url）一起发送数据。
"demo_test_post.php" 中的 PHP 脚本读取这些参数，对它们进行处理，然后返回结果。

第三个参数是回调函数。第一个回调参数存有被请求页面的内容，而第二个参数存有请求的状态。

提示： 这个 PHP 文件 ("demo_test_post.php") 类似这样：

demo_test_post.php 文件代码:
````
<?php
$name = isset($_POST['name']) ? htmlspecialchars($_POST['name']) : '';
$url = isset($_POST['url']) ? htmlspecialchars($_POST['url']) : '';
echo '网站名: ' . $name;
echo "\n";
echo 'URL 地址: ' .$url;
?>
````
