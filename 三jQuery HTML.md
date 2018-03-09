# 一 JQuery 获取内容和属性
## 1.1 获得内容- text(), html()和val()
三个简单实用的用于 DOM 操作的 jQuery 方法：
* text() - 设置或返回所选元素的文本内容
* html() - 设置或返回所选元素的内容（包括 HTML 标记）
* val() - 设置或返回表单字段的值
下面的例子演示如何通过 jQuery text() 和 html() 方法来获得内容：
````
$("#btn1").click(function(){
  alert("Text: " + $("#test").text());
});
$("#btn2").click(function(){
  alert("HTML: " + $("#test").html());
});

<p id="test">这是段落中的 <b>粗体</b> 文本。</p>
<button id="btn1">显示文本</button>
<button id="btn2">显示 HTML</button>
````
下面的例子演示如何通过 jQuery val() 方法获得输入字段的值：
````
<script>
$(document).ready(function(){
  $("button").click(function(){
    alert("值为: " + $("#test").val());
  });
});
</script>

<p>名称: <input type="text" id="test" value="菜鸟教程"></p>
<button>显示值</button>
````

## 1.2 获取属性- attr()
jQuery attr() 方法用于获取属性值。

下面的例子演示如何获得链接中 href 属性的值：
````
$("button").click(function(){
  alert($("#runoob").attr("href"));
});
````

# 二 jQuery - 设置内容和属性
## 2.1 设置内容 - text()、html() 以及 val()
* text() - 设置或返回所选元素的文本内容
* html() - 设置或返回所选元素的内容（包括 HTML 标记）
* val() - 设置或返回表单字段的值
下面的例子演示如何通过 text()、html() 以及 val() 方法来设置内容：
````
$("#btn1").click(function(){
    $("#test1").text("Hello world!");
});
$("#btn2").click(function(){
    $("#test2").html("<b>Hello world!</b>");
});
$("#btn3").click(function(){
    $("#test3").val("RUNOOB");
});
````
