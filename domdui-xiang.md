原生查找元素的方法

1.document.getElementById\('id'\);  //返回元素对象

获取元素中的内容   innerHTML

速度比较慢

2.getElementByTagName\('标签'\)   //返回的是类数组对象

node.setAttribute\('属性名'，‘属性值’\)；

3.document.getElementsByName\('name属性的值'\)   //返回的是类数组对象

4.document.getElementsByClassName\('class'\)   //\(IE9以后\)  类数组对象

5.element.querySelector\('\#c'\)   //或者   .c   //返回一个对象

element.querySelectorAll\('.class'\)    //返回一个类对象

```
var q1 = document.querySelector('#q1');
```

var x = document.getElementById\("myDIV"\);

x.querySelector\("\#demo"\).innerHTML = "Hello World!";

**插入DOM**

```
<p id="js">JavaScript</p>
<div id="list">
    <p id="java">Java</p>
    <p id="python">Python</p>
    <p id="scheme">Scheme</p>
</div>
var js = document.getElementById('js'),
    list = document.getElementById('list');
list.appendChild(js);
//变成:首先会从原先的位置删除，再插入到新的位置
<div id="list">
    <p id="java">Java</p>
    <p id="python">Python</p>
    <p id="scheme">Scheme</p>
    <p id="js">JavaScript</p>
</div>

var list = document.getElementById('list'),
    haskell = document.createElement('p');
haskell.id = 'haskell';
haskell.innerText = 'Haskell';
list.appendChild(haskell);
//结果
<div id="list">
    <p id="java">Java</p>
    <p id="python">Python</p>
    <p id="scheme">Scheme</p>
    <p id="haskell">Haskell</p>
</div>

var d = document.createElement('style');
d.setAttribute('type', 'text/css');
d.innerHTML = 'p { color: red }';
document.getElementsByTagName('head')[0].appendChild(d);

<div id="list">
    <p id="java">Java</p>
    <p id="python">Python</p>
    <p id="scheme">Scheme</p>
</div>
var list = document.getElementById('list'),
    ref = document.getElementById('python'),
    haskell = document.createElement('p');
haskell.id = 'haskell';
haskell.innerText = 'Haskell';
list.insertBefore(haskell, ref);
//结果
<div id="list">
    <p id="java">Java</p>
    <p id="haskell">Haskell</p>
    <p id="python">Python</p>
    <p id="scheme">Scheme</p>
</div>
//循环
var i, c,list = document.getElementById('list');
for (i = 0; i < list.children.length; i++) {
    c = list.children[i]; // 拿到第i个子节点
}
```

href=‘’；刷新当前页面

href=‘\#’    跳转到当前页面的起始点

href=‘\#ch’    跳转到指定的锚点

href=‘22332’    跳转到页面url为22332的页面

href=‘javascript：void\(0\)’；   不做任何页面跳转

href=‘javascript：void（f1\(\)）’     调用f1\(\)函数且不做任何页面跳转

**window浏览器**：浏览器窗口

window.innerHeight    window.innerWidth\(去处浏览器边框，菜单栏，工具栏\)

window.outerHeight   window.outerWidth\(整个浏览器的宽高\)

**navigator**：表示浏览器的信息

navigator.appName：浏览器名称；

navigator.appVersion:浏览器版本

navigator.language:浏览器设置语言

navigator.platform:操作系统类型

navigator.userAgent:浏览器设定的User-Agent字符串

```
var width = window.innerWidth || document.body.clientWidth;
```

screen:对象表示屏幕的信息。

screen.width:表示屏幕的宽度

screen.height:表示屏幕的高度

screen.colordepth:表示颜色位数

location：当前页面url的信息

```
location.href;   //http://www.example.com:8080/path/index.html?a=1&b=2#TOP
location.protocol; //'http'
location.host;   //'www.example.com'
location.port;   //'8080'
location.pathname;  //'/path/index.html'
location.search;   //'?a=1&b=2'
location.hash;  //'TOP'
```

document:表示当前页面,由于HTML在浏览器中以DOM形式表示为树形结构，document对象就是整个DOM树的根节点。

```
document.cookie;
```

history:保存了浏览器的历史记录，一般不用。用户体验不好

history.back\(\)

history.forward\(\)

