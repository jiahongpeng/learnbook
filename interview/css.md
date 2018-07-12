```
父元1.css box model是什么？.//盒子模型
```

元素的**外边距（margin）、边框（border）、内边距（padding）、内容（content）**就构成了CSS盒模型。

```css
*{
    -webkit-box-sizing: content-box;
    -moz-box-sizing: content-box;
    box-sizing: content-box;
}
```

总宽度和总高度（包括外边距、边框、内边距、内容）=宽度+外边距；

```css
.triangle {
    width : 0;
    height: 0;
    border : 100px solid transparent;
    border-top : 100px solid red; /\*这里可以设置border的top、bottom、left、right四个方向的三角\*/
}
```

2.inline element, block element, inline-block element 都有什么区别

**display:block**

block元素会独占一行，多个block元素会各自新起一行。默认情况下，block元素宽度自动填满其父元素宽度。

block元素可以设置width,height属性。块级元素即使设置了宽度,仍然是独占一行。

block元素可以设置margin和padding属性。

**display:inline**

inline元素不会独占一行，多个相邻的行内元素会排列在同一行里，直到一行排列不下，才会新换一行，其宽度随元素的内容而变化。

行内替换元素

width、 height、 margin的四个方向、 padding的四个方向都正常显示，遵循标准的css盒模型。 例如：img

行内非替换元素（重点）

width、 height不起作用，用line-height来控制高度。

padding左右起作用，上下不会影响行高，但是对于有背景色和内边距的行内非替换元素，背景可以向元素上下延伸，但是行高没有改变。因此视觉效果就是与前面的行重叠。\(《css权威指南》 P249\)

margin左右作用起作用，上下不起作用，原因在于：行内非替换元素的外边距不会改变一个元素的行高（《css权威指南》 P227）。

**display:inline-block**

简单来说就是将对象呈现为inline对象，但是对象的内容作为block对象呈现。之后的内联对象会被排列在同一行内。比如我们可以给一个link（a元素）inline-block属性值，使其既**具有block的宽度高度特性又具有inline的同行特性。**

IE6/IE7下对display:inline-block的支持性不好。

**1、inline元素的display属性设置为inline-block时，所有的浏览器都支持；**

**2、block元素的display属性设置为inline-block时，IE6/IE7浏览器是不支持的；**

对象呈递为内联对象，但是对象的内容作为块对象呈递。旁边的内联对象会被呈递在同一行，允许空格。（准确地说，应用此特性的元素现为内联对象，周围元素保持在同一行，但可以设置宽度和高度等块元素的属性）

IE中对内联元素使用display:inline-block，IE是不识别的，但使用display:inline-block在IE下会触发layout，从而使内联元素拥有了display:inline-block属性的表征。从上面的这个分析，也不难理解为什么IE下，对块元素设置display:inline-block属性无法实现inline-block的效果。这时块元素仅仅是被display:inline-block触发了layout，而它本身就是行布局，所以触发后，块元素依然还是行布局，而不会如Opera中块元素呈递为内联对象。

IE6下块元素如何实现display:inline-block的效果？  
有两种方法：  
1、 先使用display:inline-block属性触发块元素，然后再定义display:inline，让块元素呈递为内联对象（两个display 要先后放在两个CSS声明中才有效果，这是IE的一个经典bug，如果先定义了display:inline-block，然后再将display设回 inline或block，layout不会消失）。代码如下（...为省略的其他属性内容）：  
**div {display:inline-block;...}  
div {display:inline;}**  
2、直接让块元素设置为内联对象呈递（设置属性display:inline），然后触发块元素的layout（如：zoom:1 或float属性等）。代码如下：

**div { display:inline-block; \_zoom:1;\_display:inline;} /\*推荐\*/  
div { display:inline-block; \_zoom:1;\*display:inline;} /\*推荐:IE67\*/**

3.position: relative, absolute, fixed 有什么区别

1、static（静态定位）：默认值。没有定位，**元素出现在正常的流中**（忽略 top, bottom, left, right 或者 z-index 声明）。

2、relative（相对定位）：生成相对定位的元素，通过top,bottom,left,right的设置相对于其正常（原先本身）位置进行定位。可通过z-index进行层次分级。**其在文本流中的位置依然存在**

3、absolute（绝对定位）：生成绝对定位的元素，相对于**static 定位以外**的第一个**父元素**进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。可通过z-index进行层次分级。**其在正常流中的位置不再存在**

4、fixed（固定定位）：生成绝对定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。可通过z-index进行层次分级。

只有三种情况会使得元素脱离文档流，分别是：浮动，绝对定位和固定定位。

4.float:是干嘛的 如何clear float? parent div如果child divs都是float 会有什么情况发生？（parent div collapse. use overflow:hidden 可以清除）

背景，margin和padding，边框

```
  1.使用设置高度样式，清除浮动产生，前提是对象内容高度要能确定并能计算好。

  2.  <div class="divcss5"> 
        <div class="divcss5-left">left浮动</div> 
        <div class="divcss5-right">right浮动</div> 
        <div class="clear"></div> 
      </div>
      .divcss5{ width:400px;border:1px solid #F00;background:#FF0} 
      .divcss5-left,.divcss5-right{width:180px;height:100px; 
      border:1px solid #00F;background:#FFF} 
      .divcss5-left{ float:left} 
      .divcss5-right{ float:right} 
      .clear{ clear:both}
  3.  父元素加上overflow:hidden;IE中加上zoom:1
  4.  .clearfix:after{
        content: "";
        display: block;
        clear: both;
      }
      .clearfix {
        /* 触发 hasLayout */ 
        zoom: 1; 
      }
      <div class="news clearfix">
        <img src="news-pic.jpg" />
        <p>some text</p>
      </div>
```

[https://www.cnblogs.com/nxl0908/p/7245460.html](https://www.cnblogs.com/nxl0908/p/7245460.html)

5.伪元素

伪类用一个冒号来表示，而伪元素则用两个冒号来表示。

放在目标元素的子元素的前面或后面

```
 1.使用伪元素清除浮动。
 2.使用伪元素插入文本内容
 3.使用伪元素插入非文本内容/* 使用伪元素插入图片 注意：url里面的内容没有引号*/
 p:before{
   content: url(image.jpg);
 }
```

6.!important干嘛用的?一般不建议用!important.

7.css选择器优先级

（外部样式）External style sheet &lt;（内部样式）Internal style sheet &lt;（内联样式）Inline style

如果**外部样式**放在**内部样式**的**后面**，则外部样式将覆盖内部样式。

1. 内联样式表的权值最高 1000；

2. ID 选择器的权值为 100

3. Class 类选择器的权值为 10

4. HTML 标签选择器的权值为 1

**CSS优先级法则：**

A  选择器都有一个权值，权值越大越优先；

B  当权值相等时，后出现的样式表设置要优于先出现的样式表设置；

C  创作者的规则高于浏览者：即网页编写者设置的CSS 样式的优先权高于浏览器所设置的样式；

D  继承的CSS 样式不如后来指定的CSS 样式；

E  在同一组属性设置中标有“!important”规则的优先级最大；

8.居中

[http://blog.51cto.com/12917919/2090808](http://blog.51cto.com/12917919/2090808)

（1）水平居中

行内元素

```
.center-text{
    text-align: center;
}
```

块级元素水平居中

```
//方法一
.center-block {
    margin: 0 auto;
}
//方法二
.container {
    text-align: center;
}
.inline-block {
    display: inline-block;
}
//方法三
.flex-center {
    display: flex;
    justify-content: center;
}
//方法4
```

（2）垂直居中

```
//行内元素
vertical-align:middle
//已知父元素高度
#v-box {
    height: 120px;
    line-height: 120px;
}
//固定高度的块级元素
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 50%;
  height: 100px;
  margin-top: -50px; 
}
//子元素高度不确定
.center-table {
    display: table;
}
.v-cell {
    display: table-cell;
    vertical-align: middle;
}
//子元素不确定高度    
.center-flex {
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.parent {
    position: relative;
}
.child {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}

//垂直居中（父元素）
.parent {
    display: flex;
    justify-content: center;
    align-items: center;
}
.parent {
    position: absolute; 
    left: 50%; top: 50%; 
    transform: translate(-50%,-50%);
}

//利用grid（不推荐）
.parent {
  height: 140px;
  display: grid;
}
.child { 
  margin: auto;
}
//水平垂直居中
.outer {
    display: table;
    position: absolute;
    height: 100%;
    width: 100%;
}
.middle {
    display: table-cell;
    vertical-align: middle;
}
.inner {
    margin-left: auto;
    margin-right: auto;
    background: #2b2b2b;
    color:#fff;
    padding: 2rem;
    max-width: 320px;
}
<div class="outer">
    <div class="middle">
        <div class="inner">
            <p>一个好的程序员应该是那种过单行线都要往两边看的人。</p>
        </div>
    </div>
</div>
```



