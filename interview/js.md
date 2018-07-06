1.**what will happen after I input an url in a browser and hit enter?\*\*\*\*\*\*\***

第一步：客户机提出域名解析请求,并将该请求发送给本地的域名服务器。\(网址到IP地址的转换\)

第二步：当本地的域名服务器收到请求后,就先查询本地的缓存\(本地域名服务器，chrome://dns/\),如果有该纪录项,则本地的域名服务器就直接把查询的结果返回。

第三步：如果本地的缓存中没有该纪录,则本地域名服务器就直接把请求发给根域名服务器,然后根域名服务器再返回给本地域名服务器一个所查询域\(根的子域\)的主域名服务器的地址。

第四步：本地服务器再向上一步返回的域名服务器发送请求,然后接受请求的服务器查询自己的缓存,如果没有该纪录,则返回相关的下级的域名服务器的地址。

第五步：重复第四步,直到找到正确的纪录。

![](/assets/1618288278-57f00bf9444dd_articlex.png)

[https://www.cnblogs.com/engeng/articles/5943382.html](https://www.cnblogs.com/engeng/articles/5943382.html)

a. 域名解析

b. 发起TCP的3次握手（4次挥手）是关闭，

c. 建立TCP连接后发起http请求

d. 服务器端响应http请求，浏览器得到html代码

e. 浏览器解析html代码，并请求html代码中的资源

f. 浏览器对页面进行渲染呈现给用户

**2.How do you make a website faster?\*\*\*\*\*\***

[http://blog.csdn.net/wxzking/article/details/4089384](http://blog.csdn.net/wxzking/article/details/4089384)

（1）尽量少的使用标签（越多加载的东西越多）

（2）不要使用图像来表示文本

（3）不要包含不必要的 JavaScript 代码，尽可能将其外部化（浏览器会缓存外部化的文本，而（在 HTML 页面自身中）以内联方式编码的 CSS 或 JavaScript 每次都会随 HTML 一起加载。）

（4）尽可能避免使用表格（如果必须使用表格，明确地指定表格单元格、行和列的宽度和高度，否则，浏览器必须执行许多操作来计算如何显示它们，这会降低页面加载速度）

（5）可以使用许多方法来优化您的网页，包括压缩 JavaScript 文件，使用超文本传输协议（Hypertext Transfer Protocol，HTTP）压缩，以及设置图像大小。

（6）CSS sprites 可帮助减少 HTTP 请求的数量。一个图像可以包含装饰或布置页面所需的所有图像元素。您使用 CSS 来选择（通过调用某些位置和维度）用于特定元素的映射。

```
    【1】减少http请求次数
    【2】减少图片大小，提升网页加载速度 \(多张图片加载速度小于拼合成的图片的加载速度\)
```

字体图标：[https://github.com/jiahongpeng/learnbook/blob/master/Font-Awesome-master.zip](https://github.com/jiahongpeng/learnbook/blob/master/Font-Awesome-master.zip)

（7）按需加载javascript

[https://www.cnblogs.com/mamimi/p/7646358.html](https://www.cnblogs.com/mamimi/p/7646358.html)

RequireJS

SeaJS

![](/assets/1016870-20171009133914402-2006851883.jpg)

**3.GET 和 POST区别\*\*\*\*\*\***

4.what's cookie and how tow set it?

cookie 是存储于访问者的计算机中的变量。每当同一台计算机通过浏览器请求某个页面时，就会发送这个 cookie。你可以使用 JavaScript 来创建和取回 cookie 的值。

cookie 是访问过的网站创建的文件，用于存储浏览信息，例如个人资料信息。

[https://www.cnblogs.com/Darren\_code/archive/2011/11/24/Cookie.html\#!comments](https://www.cnblogs.com/Darren_code/archive/2011/11/24/Cookie.html#!comments)

5.what's iframe?

6.what's csrf?

7.javascript中call，apply，bind总结

[https://www.cnblogs.com/pssp/p/5215621.html](https://www.cnblogs.com/pssp/p/5215621.html)

