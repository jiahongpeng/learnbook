1.what will happen after I input an url in a browser and hit enter?

第一步：客户机提出域名解析请求,并将该请求发送给本地的域名服务器。

第二步：当本地的域名服务器收到请求后,就先查询本地的缓存,如果有该纪录项,则本地的域名服务器就直接把查询的结果返回。

第三步：如果本地的缓存中没有该纪录,则本地域名服务器就直接把请求发给根域名服务器,然后根域名服务器再返回给本地域名服务器一个所查询域\(根的子域\)的主域名服务器的地址。

第四步：本地服务器再向上一步返回的域名服务器发送请求,然后接受请求的服务器查询自己的缓存,如果没有该纪录,则返回相关的下级的域名服务器的地址。

第五步：重复第四步,直到找到正确的纪录。

2.How do you make a website faster?

3.GET 和 POST区别

4.what's cookie and how tow set it?

  
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
margin-top:72.0000pt;  
margin-bottom:72.0000pt;  
margin-left:90.0000pt;  
margin-right:90.0000pt;  
size:595.3000pt 841.9000pt;  
layout-grid:15.6000pt;  
}  
div.Section0{page:Section0;}

5.what's iframe?.

6.what's csrf? \(其实不太长考但是最好知道，我大概被问了两次？\)



