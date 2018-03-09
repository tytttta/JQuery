# 一 JQuery效果

## 1.1 jQuery hide() 和 show()
通过jQuery，可以使用hide()和show()来隐藏和显示HTML元素
````
$("#hide").click(function(){
  $("p").hide();
});
 
$("#show").click(function(){
  $("p").show();
});
````
语法：
````
$(selector).hide(speed,callback);

$(selector).show(speed,callback);
````
可选参数speed规定隐藏/显示的速度，可以取“slow”，“fast”或毫秒。

可选参数callback是隐藏或显示完成后所执行的函数名称。

## 1.2 jQuery toggle()
通过toggle()方法来切换hide()和show()方法。
````
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("p").toggle();
  });
});
</script>
</head>
<body>
<button>隐藏/显示</button>
<p>这是一个文本段落。</p>
<p>这是另外一个文本段落。</
````
语法：
````
$(selector).toggle(speed,callback);
````
可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是隐藏或显示完成后所执行的函数名称。


# 二 jQuery 淡入淡出

## 2.1 jQuery fading 方法
jQuery有下面四种fade方法：
* fadeIn()
* fadeOut()
* fadeToggle()
* fadeTo()

## 2.2 jQuery fadeIn()方法
用于淡入已隐藏的元素。

语法:
````
$(selector).fadeIn(speed,callback);
````
可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。.

可选的 callback 参数是 fading 完成后所执行的函数名称。

下面的例子演示了带有不同参数的 fadeIn() 方法：
````
$("button").click(function(){
  $("#div1").fadeIn();
  $("#div2").fadeIn("slow");
  $("#div3").fadeIn(3000);
});
<button>点击淡入 div 元素。</button>
<br><br>
<div id="div1" style="width:80px;height:80px;display:none;background-color:red;"></div><br>
<div id="div2" style="width:80px;height:80px;display:none;background-color:green;"></div><br>
<div id="div3" style="width:80px;height:80px;display:none;background-color:blue;"></div>
````

## 2.3 jQuery fadeOut()方法
用于淡出可见元素。
语法:
````
$(selector).fadeOut(speed,callback);
````
可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是 fading 完成后所执行的函数名称。

下面的例子演示了带有不同参数的 fadeOut() 方法：
````
$("button").click(function(){
  $("#div1").fadeOut();
  $("#div2").fadeOut("slow");
  $("#div3").fadeOut(3000);
});
````

## 2.4 jQuery fadeToggle()方法
可以在fadeIn()和fadeOut()方法之间进行切换。

如果元素已淡出，则 fadeToggle() 会向元素添加淡入效果。

如果元素已淡入，则 fadeToggle() 会向元素添加淡出效果。

语法:
````
$(selector).fadeToggle(speed,callback);
````
可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是 fading 完成后所执行的函数名称。

下面的例子演示了带有不同参数的 fadeToggle() 方法：
````
$("button").click(function(){
  $("#div1").fadeToggle();
  $("#div2").fadeToggle("slow");
  $("#div3").fadeToggle(3000);
});
````

## 2.5 jQuery fadeTo()方法
允许渐变为给定的不透明度（值介于0和1之间）

语法:
````
$(selector).fadeTo(speed,opacity,callback);
````
必需的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

fadeTo() 方法中必需的 opacity 参数将淡入淡出效果设置为给定的不透明度（值介于 0 与 1 之间）。

可选的 callback 参数是该函数完成后所执行的函数名称。

下面的例子演示了带有不同参数的 fadeTo() 方法：
````
$("button").click(function(){
  $("#div1").fadeTo("slow",0.15);
  $("#div2").fadeTo("slow",0.4);
  $("#div3").fadeTo("slow",0.7);
});
````

# 三 jQuery 滑动
## 3.1 jQuery 有以下滑动方法：
* slideDown()
* slideUp()
* slideToggle()

## 3.2 jQuery slideDown()方法
jQuery slideDown() 方法用于向下滑动元素。

语法:
````
$(selector).slideDown(speed,callback);
````
可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是滑动完成后所执行的函数名称。

下面的例子演示了 slideDown() 方法：
````
<script> 
$(document).ready(function(){
  $("#flip").click(function(){
    $("#panel").slideDown("slow");
  });
});
</script>
 
<style type="text/css"> 
#panel,#flip
{
	padding:5px;
	text-align:center;
	background-color:#e5eecc;
	border:solid 1px #c3c3c3;
}
#panel
{
	padding:50px;
	display:none;
}
</style>
 
<div id="flip">点我滑下面板</div>
<div id="panel">Hello world!</div>
````

## 3.3 jQuery slideUp()方法
jQuery slideUp() 方法用于向上滑动元素。

语法:
````
$(selector).slideUp(speed,callback);
````
可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是滑动完成后所执行的函数名称。

下面的例子演示了 slideUp() 方法：
````
<script> 
$(document).ready(function(){
  $("#flip").click(function(){
    $("#panel").slideUp("slow");
  });
});
</script>
 
<style type="text/css"> 
#panel,#flip
{
	padding:5px;
	text-align:center;
	background-color:#e5eecc;
	border:solid 1px #c3c3c3;
}
#panel
{
	padding:50px;
}
</style>
 
<div id="flip">点我拉起面板</div>
<div id="panel">Hello world!</div>
````

## 3.4 jQuery slideToggle()方法
jQuery slideToggle() 方法可以在 slideDown() 与 slideUp() 方法之间进行切换。

如果元素向下滑动，则 slideToggle() 可向上滑动它们。

如果元素向上滑动，则 slideToggle() 可向下滑动它们。
````
$(selector).slideToggle(speed,callback);
````
可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是滑动完成后所执行的函数名称。

下面的例子演示了 slideToggle() 方法：
````
$("#flip").click(function(){
  $("#panel").slideToggle();
});
````

# 四  jQuery 动画
## 4.1 jQuery animate()方法用于创建自定义动画
语法:
````
$(selector).animate({params},speed,callback);
````
必需的 params 参数定义形成动画的 CSS 属性。

可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是动画完成后所执行的函数名称。

下面的例子演示 animate() 方法的简单应用。它把 <div> 元素往右边移动了 250 像素：
````
<script> 
$(document).ready(function(){
  $("button").click(function(){
    $("div").animate({left:'250px'});
  });
});
</script>
<button>开始动画</button>
<p>默认情况下，所有的 HTML 元素有一个静态的位置，且是不可移动的。 
如果需要改变为，我们需要将元素的 position 属性设置为 relative, fixed, 或 absolute!</p>
<div style="background:#98bf21;height:100px;width:100px;position:absolute;">
</div>
````
**默认情况下，所有的 HTML 元素有一个静态的位置，且是不可移动的。 
如果需要改变为，我们需要将元素的 position 属性设置为 relative, fixed, 或 absolute!**

## 4.2 jQuery animate() 操作多个属性
````
$("button").click(function(){
  $("div").animate({
    left:'250px',
    opacity:'0.5',
    height:'150px',
    width:'150px'
  });
});
````
**可以用 animate() 方法来操作所有 CSS 属性,但是当使用 animate() 时，必须使用 Camel 标记法书写所有的属性名，比如，必须使用 paddingLeft 
而不是 padding-left，使用 marginRight 而不是 margin-right，等等。同时，色彩动画并不包含在核心 jQuery 库中。**

## 4.3 jQuery animate() - 使用相对值
也可以定义相对值（该值相对于元素的当前值）。需要在值的前面加上 += 或 -=：
````
$("button").click(function(){
  $("div").animate({
    left:'250px',
    height:'+=150px',
    width:'+=150px'
  });
});
````

## 4.4 jQuery animate() - 使用预定义的值
您甚至可以把属性的动画值设置为 "show"、"hide" 或 "toggle"：
````
$("button").click(function(){
  $("div").animate({
    height:'toggle'
  });
});
````

## 4.5 Query animate() - 使用队列功能
默认地，jQuery 提供针对动画的队列功能。

这意味着如果在彼此之后编写多个 animate() 调用，jQuery 会创建包含这些方法调用的"内部"队列。然后逐一运行这些 animate 调用。

实例 1
````
$("button").click(function(){
  var div=$("div");
  div.animate({height:'300px',opacity:'0.4'},"slow");
  div.animate({width:'300px',opacity:'0.8'},"slow");
  div.animate({height:'100px',opacity:'0.4'},"slow");
  div.animate({width:'100px',opacity:'0.8'},"slow");
});
````

下面的例子把 <div> 元素往右边移动了 100 像素，然后增加文本的字号：
````
$("button").click(function(){
  var div=$("div");
  div.animate({left:'100px'},"slow");
  div.animate({fontSize:'3em'},"slow");
});
````


# 五 jQuery停止动画
## 5.1 jQuery stop()方法
方法用于停止动画或效果，在它们完成之前。

stop() 方法适用于所有 jQuery 效果函数，包括滑动、淡入淡出和自定义动画。

语法:
````
$(selector).stop(stopAll,goToEnd);
````
可选的 stopAll 参数规定是否应该清除动画队列。默认是 false，即仅停止活动的动画，允许任何排入队列的动画向后执行。

可选的 goToEnd 参数规定是否立即完成当前动画。默认是 false。

因此，默认地，stop() 会清除在被选元素上指定的当前动画。

下面的例子演示 stop() 方法：
````
<script> 
$(document).ready(function(){
  $("#start").click(function(){
    $("div").animate({left:'100px'},5000);
    $("div").animate({fontSize:'3em'},5000);
  });
  
  $("#stop").click(function(){
    $("div").stop();
  });

  $("#stop2").click(function(){
    $("div").stop(true);
  });

  $("#stop3").click(function(){
    $("div").stop(true,true);
  });
  
});
</script> 
<button id="start">开始</button>
<button id="stop">停止</button>
<button id="stop2">停止所有</button>
<button id="stop3">停止动画，但完成动作</button>
<p>点击 "开始" 按钮开始动画。</p>
<p>点击 "停止" 按钮停止当前激活的动画，但之后我们能再动画队列中再次激活。</p>
<p>点击 "停止所有" 按钮停止当前动画，并清除动画队列，所以元素的所有动画都会停止。</p>
<p>点击 "停止动画，但完成动作" 快速完成动作，并停止它。</p> 

<div style="background:#98bf21;height:100px;width:200px;position:absolute;">HELLO</div>
````

# 六 jQuery Callback方法
Callback 函数在当前动画 100% 完成之后执行。
## 6.1 jQuery 动画的问题
许多 jQuery 函数涉及动画。这些函数也许会将 speed 或 duration 作为可选参数。

例子：$("p").hide("slow")

speed 或 duration 参数可以设置许多不同的值，比如 "slow", "fast", "normal" 或毫秒。

**以下实例在隐藏效果完全实现后回调函数:**

使用 callback 实例
````
$("button").click(function(){
  $("p").hide("slow",function(){
    alert("段落现在被隐藏了");
  });
});
````

**以下实例没有回调函数，警告框会在隐藏效果完成前弹出：**

没有 callback(回调)
````
$("button").click(function(){
  $("p").hide(1000);
  alert("段落现在被隐藏了");
});
````

# 七 jQuery 链(Chaining)
通过 jQuery，可以把动作/方法链接在一起。

Chaining 允许我们在一条语句中运行多个 jQuery 方法（在相同的元素上）

# 7.1 jQuery 方法链接
直到现在，我们都是一次写一条 jQuery 语句（一条接着另一条）。 
不过，有一种名为链接（chaining）的技术，允许我们在相同的元素上运行多条 jQuery 命令，一条接着另一条。

**提示：** 这样的话，浏览器就不必多次查找相同的元素。

如需链接一个动作，您只需简单地把该动作追加到之前的动作上。

下面的例子把 css()、slideUp() 和 slideDown() 链接在一起。"p1" 元素首先会变为红色，然后向上滑动，再然后向下滑动：
````
$("#p1").css("color","red").slideUp(2000).slideDown(2000);
````
如果需要，我们也可以添加多个方法调用。

**提示：** 当进行链接时，代码行会变得很差。不过，jQuery 语法不是很严格；您可以按照希望的格式来写，包含换行和缩进。

如下书写也可以很好地运行：
````
$("#p1").css("color","red")
  .slideUp(2000)
  .slideDown(2000);
````
jQuery 会抛掉多余的空格，并当成一行长代码来执行上面的代码行。
