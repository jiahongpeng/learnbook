1.css box model是什么？.//盒子模型

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

2.  
@font-face{  
font-family:"Times New Roman";  
}  
  
@font-face{  
font-family:"宋体";  
}  
  
@font-face{  
font-family:"Calibri";  
}  
  
@font-face{  
font-family:"微软雅黑";  
}  
  
p.MsoNormal{  
mso-style-name:正文;  
mso-style-parent:"";  
margin:0pt;  
margin-bottom:.0001pt;  
mso-pagination:none;  
text-align:justify;  
text-justify:inter-ideograph;  
font-family:Calibri;  
mso-fareast-font-family:宋体;  
mso-bidi-font-family:'Times New Roman';  
font-size:10.5000pt;  
mso-font-kerning:1.0000pt;  
}  
  
span.msoIns{  
mso-style-type:export-only;  
mso-style-name:"";  
text-decoration:underline;  
text-underline:single;  
color:blue;  
}  
  
span.msoDel{  
mso-style-type:export-only;  
mso-style-name:"";  
text-decoration:line-through;  
color:red;  
}  
@page{mso-page-border-surround-header:no;  
	mso-page-border-surround-footer:no;}@page Section0{  
}  
div.Section0{page:Section0;}

inline element, block element, inline-block element 都有什么区别

display:block

block元素会独占一行，多个block元素会各自新起一行。默认情况下，block元素宽度自动填满其父元素宽度。

block元素可以设置width,height属性。块级元素即使设置了宽度,仍然是独占一行。

block元素可以设置margin和padding属性。

display:inline

inline元素不会独占一行，多个相邻的行内元素会排列在同一行里，直到一行排列不下，才会新换一行，其宽度随元素的内容而变化。

行内替换元素

width、 height、 margin的四个方向、 padding的四个方向都正常显示，遵循标准的css盒模型。 例如：img

行内非替换元素（重点）

width、 height不起作用，用line-height来控制高度。

padding左右起作用，上下不会影响行高，但是对于有背景色和内边距的行内非替换元素，背景可以向元素上下延伸，但是行高没有改变。因此视觉效果就是与前面的行重叠。\(《css权威指南》 P249\)

margin左右作用起作用，上下不起作用，原因在于：行内非替换元素的外边距不会改变一个元素的行高（《css权威指南》 P227）。

display:inline-block

简单来说就是将对象呈现为inline对象，但是对象的内容作为block对象呈现。之后的内联对象会被排列在同一行内。比如我们可以给一个link（a元素）inline-block属性值，使其既具有block的宽度高度特性又具有inline的同行特性。

IE6/IE7下对display:inline-block的支持性不好。

1、inline元素的display属性设置为inline-block时，所有的浏览器都支持；

2、block元素的display属性设置为inline-block时，IE6/IE7浏览器是不支持的；

 对象呈递为内联对象，但是对象的内容作为块对象呈递。旁边的内联对象会被呈递在同一行，允许空格。（准确地说，应用此特性的元素现为内联对象，周围元素保持在同一行，但可以设置宽度和高度等块元素的属性）

 IE中对内联元素使用display:inline-block，IE是不识别的，但使用display:inline-block在IE下会触发layout，从而使内联元素拥有了display:inline-block属性的表征。从上面的这个分析，也不难理解为什么IE下，对块元素设置display:inline-block属性无法实现inline-block的效果。这时块元素仅仅是被display:inline-block触发了layout，而它本身就是行布局，所以触发后，块元素依然还是行布局，而不会如Opera中块元素呈递为内联对象。

IE6下块元素如何实现display:inline-block的效果？  
有两种方法：  
1、 先使用display:inline-block属性触发块元素，然后再定义display:inline，让块元素呈递为内联对象（两个display 要先后放在两个CSS声明中才有效果，这是IE的一个经典bug，如果先定义了display:inline-block，然后再将display设回 inline或block，layout不会消失）。代码如下（...为省略的其他属性内容）：  
div {display:inline-block;...}  
div {display:inline;}  
2、直接让块元素设置为内联对象呈递（设置属性display:inline），然后触发块元素的layout（如：zoom:1 或float属性等）。代码如下：  
  
div { display:inline-block; \_zoom:1;\_display:inline;} /\*推荐\*/  
div { display:inline-block; \_zoom:1;\*display:inline;} /\*推荐:IE67\*/

