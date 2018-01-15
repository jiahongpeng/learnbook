  
@font-face{  
font-family:"Times New Roman";  
}  
  
@font-face{  
font-family:"宋体";  
}  
  
@font-face{  
font-family:"Courier New";  
}  
  
@font-face{  
font-family:"Calibri";  
}  
  
@font-face{  
font-family:"微软雅黑";  
}  
  
@list l0:level1{  
mso-level-number-format:decimal;  
mso-level-suffix:tab;  
mso-level-text:"%1.";  
mso-level-tab-stop:15.6000pt;  
mso-level-number-position:left;  
margin-left:0.0000pt;  
text-indent:0.0000pt;  
font-family:'Times New Roman';}  
  
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
  
span.10{  
font-family:'Times New Roman';  
}  
  
span.15{  
font-family:'Times New Roman';  
font-weight:bold;  
}  
  
p.pre{  
mso-style-name:"HTML 预设格式";  
margin:0pt;  
margin-bottom:.0001pt;  
mso-pagination:none;  
text-align:left;  
font-family:'Courier New';  
mso-fareast-font-family:宋体;  
font-size:10.0000pt;  
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

1.css box model是什么？.//盒子模型

元素的**外边距（margin）、边框（border）、内边距（padding）、内容（content）**就构成了CSS盒模型。

\*{

  -webkit-box-sizing: content-box;

  -moz-box-sizing: content-box;

  box-sizing: content-box;

}

总宽度和总高度（包括外边距、边框、内边距、内容）=宽度+外边距；

.triangle {

width : 0;

      height: 0;

      border : 100px solid transparent;

      border-top : 100px solid red; /\*这里可以设置border的top、bottom、left、right四个方向的三角\*/

}

