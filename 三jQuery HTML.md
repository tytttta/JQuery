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

## 2.2 text()、html() 以及 val() 的回调函数
上面的三个 jQuery 方法：text()、html() 以及 val()，同样拥有回调函数。回调函数有两个参数：被选元素列表中当前元素的下标，以及原始（旧的）值。然后以函数新值返回您希望使用的字符串。

下面的例子演示带有回调函数的 text() 和 html()：
````
$("#btn1").click(function(){
    $("#test1").text(function(i,origText){
        return "旧文本: " + origText + " 新文本: Hello world! (index: " + i + ")"; 
    });
});
 
$("#btn2").click(function(){
    $("#test2").html(function(i,origText){
        return "旧 html: " + origText + " 新 html: Hello <b>world!</b> (index: " + i + ")"; 
    });
});

<p id="test1">这是一个有 <b>粗体</b> 字的段落。</p>
<p id="test2">这是另外一个有 <b>粗体</b> 字的段落。</p>
<button id="btn1">显示 新/旧 文本</button>
<button id="btn2">显示 新/旧 HTML</button>
````
**note: http://www.cnblogs.com/hcxy/p/6882916.html**


## 2.3 设置属性 - attr()
jQuery attr() 方法也用于设置/改变属性值。

下面的例子演示如何改变（设置）链接中 href 属性的值：
````
$("button").click(function(){
 $("#runoob").attr("href","http://www.runoob.com/jquery")
 });
 ````
 attr() 方法也允许您同时设置多个属性。

下面的例子演示如何同时设置 href 和 title 属性：
````
$("button").click(function(){
  $("#runoob").attr({
  "href":"http://www.runoob.com/jquery",
  "title":"jquery"
  });
 });
 ````
 ## 2.4 attr()的回调函数
jQuery 方法 attr()，也提供回调函数。回调函数有两个参数：被选元素列表中当前元素的下标，以及原始（旧的）值。然后以函数新值返回您希望使用的字符串。

下面的例子演示带有回调函数的 attr() 方法：
````
$("button").click(function(){
   $("#runoob").attr("href",function(i,origValue){
      return origValue+"/jquery";
    });
 });
 ````
 
 # 3 jQuery - 添加元素
  通过 jQuery，可以很容易地添加新元素/内容。

## 3.1 添加新的 HTML 内容
  我们将学习用于添加新内容的四个 jQuery 方法：

  * append() - 在被选元素的结尾插入内容
  * prepend() - 在被选元素的开头插入内容
  * after() - 在被选元素之后插入内容
  * before() - 在被选元素之前插入内容
  
## 3.2 jQuery append() 方法
jQuery append() 方法在被选元素的结尾插入内容（仍然该元素的内部）。
````
$("p").append("追加文本");
````
## 3.3 jQuery prepend() 方法
jQuery prepend() 方法在被选元素的开头插入内容。
````
$("P").prepend("在开头追加文本");
````
## 3.3 通过 append() 和 prepend() 方法添加若干新元素
在上面的例子中，我们只在被选元素的开头/结尾插入文本/HTML。

不过，append() 和 prepend() 方法能够通过参数接收无限数量的新元素。可以通过 jQuery 来生成文本/HTML（就像上面的例子那样），或者通过 JavaScript 代码和 DOM 元素。

在下面的例子中，我们创建若干个新元素。这些元素可以通过 text/HTML、jQuery 或者 JavaScript/DOM 来创建。然后我们通过 append() 方法把这些新元素追加到文本中（对 prepend() 同样有效）：
````
function appendText(){
 var txt1="<p>文本。</p>";              // 使用 HTML 标签创建文本
    var txt2=$("<p></p>").text("文本。");  // 使用 jQuery 创建文本
    var txt3=document.createElement("p");
    txt3.innerHTML="文本。";               // 使用 DOM 创建文本 text with DOM
    $("body").append(txt1,txt2,txt3);        // 追加新元素
}
````
## 3.4 jQuery after() 和 before() 方法
jQuery after() 方法在被选元素之后插入内容。

jQuery before() 方法在被选元素之前插入内容。
````
$("img").after("在后面添加文本");
 
$("img").before("在前面添加文本");
````
## 3.5 通过 after() 和 before() 方法添加若干新元素
after() 和 before() 方法能够通过参数接收无限数量的新元素。可以通过 text/HTML、jQuery 或者 JavaScript/DOM 来创建新元素。

在下面的例子中，我们创建若干新元素。这些元素可以通过 text/HTML、jQuery 或者 JavaScript/DOM 来创建。然后我们通过 after() 方法把这些新元素插到文本中（对 before() 同样有效）：
````
function afterText()
{
    var txt1="<b>I </b>";                    // 使用 HTML 创建元素
    var txt2=$("<i></i>").text("love ");     // 使用 jQuery 创建元素
    var txt3=document.createElement("big");  // 使用 DOM 创建元素
    txt3.innerHTML="jQuery!";
    $("img").after(txt1,txt2,txt3);          // 在图片后添加文本
}
````
 **append/prepend 是在选择元素内部嵌入。**
 
**after/before 是在元素外面追加。**

# 4 jQuery - 删除元素
通过 jQuery，可以很容易地删除已有的 HTML 元素。

 ## 4.1 删除元素/内容
如需删除元素和内容，一般可使用以下两个 jQuery 方法：

remove() - 删除被选元素（及其子元素）
empty() - 从被选元素中删除子元素

## 4.2 jQuery remove() 方法
jQuery remove() 方法删除被选元素及其子元素。
````
$("#div1").remove();
````

## 4.3 jQuery empty() 方法
jQuery empty() 方法删除被选元素的子元素。
````
$("#div1").empty();
````

## 4.4 过滤被删除的元素
jQuery remove() 方法也可接受一个参数，允许您对被删元素进行过滤。该参数可以是任何 jQuery 选择器的语法。

下面的例子删除 class="italic" 的所有 <p> 元素：
````
  $("p").remove(".italic");
````
# 5 jQuery - 获取并设置 CSS 类
通过 jQuery，可以很容易地对 CSS 元素进行操作
  
## 5.1 Query 操作 CSS
jQuery 拥有若干进行 CSS 操作的方法。我们将学习下面这些：

addClass() - 向被选元素添加一个或多个类
removeClass() - 从被选元素删除一个或多个类
toggleClass() - 对被选元素进行添加/删除类的切换操作
css() - 设置或返回样式属性


**实例样式表**

下面的样式表将用于本页的所有例子：
````
.important
{
        font-weight:bold;
        font-size:xx-large;
}
 
.blue
{
        color:blue;
}
````
## 5.2 jQuery addClass() 方法
下面的例子展示如何向不同的元素添加 class 属性。当然，在添加类时，您也可以选取多个元素：
````
$("button").click(function(){
  $("h1,h2,p").addClass("blue");
  $("div").addClass("important");
});
````
也可以在 addClass() 方法中规定多个类：
````
$("button").click(function(){
  $("body div:first").addClass("important blue");
});
````

## 5.3 jQuery removeClass() 方法
下面的例子演示如何在不同的元素中删除指定的 class 属性：
````
$("button").click(function(){
  $("h1,h2,p").removeClass("blue");
});
````

## 5.4 jQuery toggleClass() 方法
下面的例子将展示如何使用 jQuery toggleClass() 方法。该方法对被选元素进行添加/删除类的切换操作：
````
$("button").click(function(){
  $("h1,h2,p").toggleClass("blue");
});
````

## 5.5 jQuery css() 方法
css() 方法设置或返回被选元素的一个或多个样式属性。

### 5.5.1 返回 CSS 属性
如需返回指定的 CSS 属性的值，请使用如下语法：

css("propertyname");
下面的例子将返回匹配元素的 background-color 值：**如果有多个会选择首个元素**
````
#("p").css("background-color");

<p style="background-color:#ff0000">这是一个段落。</p>
````

### 5.5.2 设置 CSS 属性
如需设置指定的 CSS 属性，请使用如下语法：

css("propertyname","value");
下面的例子将为所有匹配元素设置 background-color 值：
````
$("p").css("background-color","yellow");
````
### 5.5.3 设置多个 CSS 属性
如需设置多个 CSS 属性，请使用如下语法：
````
css({"propertyname":"value","propertyname":"value",...});
````
下面的例子将为所有匹配元素设置 background-color 和 font-size：
````
$("p").css({"background-color":"yellow","font-size":"200%"});
````

# 5 jQuery 尺寸
通过 jQuery，很容易处理元素和浏览器窗口的尺寸。
jQuery 提供多个处理尺寸的重要方法：
* width()
* height()
* innerWidth()
* innerHeight()
* outerWidth()
* outerHeight()

以下是jQuery尺寸图片：

![jQuery尺寸](https://github.com/tytttta/JQuery/blob/master/jquery_struct.png)

## 5.1 jQuery width() 和 height() 方法
width() 方法设置或返回元素的宽度（不包括内边距、边框或外边距）。

height() 方法设置或返回元素的高度（不包括内边距、边框或外边距）。

下面的例子返回指定的 \<div> 元素的宽度和高度：
````
$("button").click(function(){
  var txt="";
  txt+="div 的宽度是: " + $("#div1").width() + "</br>";
  txt+="div 的高度是: " + $("#div1").height();
  $("#div1").html(txt);
});
````

## 5.2 jQuery innerWidth() 和 innerHeight() 方法
innerWidth() 方法返回元素的宽度（包括内边距）。

innerHeight() 方法返回元素的高度（包括内边距）。

下面的例子返回指定的 \<div> 元素的 inner-width/height：
````
$("button").click(function(){
  var txt="";
  txt+="div 宽度，包含内边距: " + $("#div1").innerWidth() + "</br>";
    txt+="div 高度，包含内边距: " + $("#div1").innerHeight();
  $("#div1").html(txt);
});
````

## 5.3 jQuery outerWidth() 和 outerHeight() 方法
outerWidth() 方法返回元素的宽度（包括内边距和边框）。

outerHeight() 方法返回元素的高度（包括内边距和边框）。

下面的例子返回指定的 \<div> 元素的 outer-width/height：
````
$("button").click(function(){
  var txt="";
  txt+="div 宽度，包含内边距和边框: " + $("#div1").outerWidth() + "</br>";
  txt+="div 高度，包含内边距和边框: " + $("#div1").outerHeight();
  $("#div1").html(txt);
});
````
