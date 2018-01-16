**1.what will happen after I input an url in a browser and hit enter?\*\*\*\*\*\*\***

第一步：客户机提出域名解析请求,并将该请求发送给本地的域名服务器。

第二步：当本地的域名服务器收到请求后,就先查询本地的缓存,如果有该纪录项,则本地的域名服务器就直接把查询的结果返回。

第三步：如果本地的缓存中没有该纪录,则本地域名服务器就直接把请求发给根域名服务器,然后根域名服务器再返回给本地域名服务器一个所查询域\(根的子域\)的主域名服务器的地址。

第四步：本地服务器再向上一步返回的域名服务器发送请求,然后接受请求的服务器查询自己的缓存,如果没有该纪录,则返回相关的下级的域名服务器的地址。

第五步：重复第四步,直到找到正确的纪录。

**2.How do you make a website faster?\*\*\*\*\*\***

[http://blog.csdn.net/wxzking/article/details/4089384](http://blog.csdn.net/wxzking/article/details/4089384)

**3.GET 和 POST区别\*\*\*\*\*\***

4.what's cookie and how tow set it?

cookie 是存储于访问者的计算机中的变量。每当同一台计算机通过浏览器请求某个页面时，就会发送这个 cookie。你可以使用 JavaScript 来创建和取回 cookie 的值。

5.what's iframe?

6.what's csrf?

7.javascript中call，apply，bind总结



