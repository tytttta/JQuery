# 一 jQuery其他

## 1.1 Query 和其他 JavaScript 框架
正如您已经了解到的，jQuery 使用 $ 符号作为 jQuery 的简写。

**如果其他 JavaScript 框架也使用 $ 符号作为简写怎么办？**

其他一些 JavaScript 框架包括：MooTools、Backbone、Sammy、Cappuccino、Knockout、JavaScript MVC、Google Web Toolkit、Google Closure、Ember、Batman 以及 Ext JS。

其中某些框架也使用 $ 符号作为简写（就像 jQuery），如果您在用的两种不同的框架正在使用相同的简写符号，有可能导致脚本停止运行。

jQuery 的团队考虑到了这个问题，并实现了 noConflict() 方法。

## 1.2 Query noConflict() 方法
noConflict() 方法会释放对 $ 标识符的控制，这样其他脚本就可以使用它了。

当然，您仍然可以通过全名替代简写的方式来使用 jQuery：

实例
````
$.noConflict();
jQuery(document).ready(function(){
  jQuery("button").click(function(){
    jQuery("p").text("jQuery 仍然在工作!");
  });
});
````

您也可以创建自己的简写。noConflict() 可返回对 jQuery 的引用，您可以把它存入变量，以供稍后使用。请看这个例子：

````
var jq = $.noConflict();
jq(document).ready(function(){
  jq("button").click(function(){
    jq("p").text("jQuery 仍然在工作!");
  });
});
````
如果你的 jQuery 代码块使用 $ 简写，并且您不愿意改变这个快捷方式，那么您可以把 $ 符号作为变量传递给 ready 方法。
这样就可以在函数内使用 $ 符号了 - 而在函数外，依旧不得不使用 "jQuery"：
````
$.noConflict();
jQuery(document).ready(function($){
  $("button").click(function(){
    $("p").text("jQuery 仍然在工作!");
  });
````

# 二 JSONP 教程
Jsonp(JSON with Padding) 是 json 的一种"使用模式"，可以让网页从别的域名（网站）那获取资料，即跨域读取数据。

为什么我们从不同的域（网站）访问数据需要一个特殊的技术(JSONP )呢？这是因为同源策略。

同源策略，它是由Netscape提出的一个著名的安全策略，现在所有支持JavaScript 的浏览器都会使用这个策略。
});

## 2.1 JSONP 应用
**服务端JSONP格式数据**
如客户想访问 : http://www.runoob.com/try/ajax/jsonp.php?jsonp=callbackFunction。

假设客户期望返回JSON数据：["customername1","customername2"]。

真正返回到客户端的数据显示为: callbackFunction(["customername1","customername2"])。

服务端文件jsonp.php代码为：

jsonp.php 文件代码
````
<?php
header('Content-type: application/json');
//获取回调函数名
$jsoncallback = htmlspecialchars($_REQUEST ['jsoncallback']);
//json数据
$json_data = '["customername1","customername2"]';
//输出jsonp格式的数据
echo $jsoncallback . "(" . $json_data . ")";
?>
````
**客户端实现 callbackFunction 函数**
````
<script type="text/javascript">
function callbackFunction(result, methodName)
{
    var html = '<ul>';
    for(var i = 0; i < result.length; i++)
    {
        html += '<li>' + result[i] + '</li>';
    }
    html += '</ul>';
    document.getElementById('divCustomers').innerHTML = html;
}
</script>
````
**页面展示**
````
<div id="divCustomers"></div>
````
**客户端页面完整代码**
````
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JSONP 实例</title>
</head>
<body>
    <div id="divCustomers"></div>
    <script type="text/javascript">
function callbackFunction(result, methodName)
        {
            var html = '<ul>';
            for(var i = 0; i < result.length; i++)
            {
                html += '<li>' + result[i] + '</li>';
            }
            html += '</ul>';
            document.getElementById('divCustomers').innerHTML = html;
        }
</script>
<script type="text/javascript" src="http://www.runoob.com/try/ajax/jsonp.php?jsoncallback=callbackFunction"></script>
</body>
</html>
````
**jQuery 使用 JSONP**
以上代码可以使用 jQuery 代码实例：
````
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>JSONP 实例</title>
    <script src="http://cdn.static.runoob.com/libs/jquery/1.8.3/jquery.js"></script>    
</head>
<body>
<div id="divCustomers"></div>
<script>
$.getJSON("http://www.runoob.com/try/ajax/jsonp.php?jsoncallback=?", function(data) {
    
    var html = '<ul>';
    for(var i = 0; i < data.length; i++)
    {
        html += '<li>' + data[i] + '</li>';
    }
    html += '</ul>';
    
    $('#divCustomers').html(html); 
});
</script>
</body>
</html>
````

**其他内容请参见http://www.runoob.com/jquery/jquery-plugin-validate.html**

