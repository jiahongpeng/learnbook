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



