```
<script language="JavaScript" type="text/javascript"> 
    //设置两个cookie 
    document.cookie="userId=828"; 
    document.cookie="userName=hulk"; 
    //获取cookie字符串 
    var strCookie=document.cookie; 
    //将多cookie切割为多个名/值对 
    var arrCookie=strCookie.split("; "); 
    var userId; 
    //遍历cookie数组，处理每个cookie对 
    for(var i=0;i<arrCookie.length;i++){ 
        var arr=arrCookie[i].split("="); 
        //找到名称为userId的cookie，并返回它的值 
        if("userId"==arr[0]){ 
            userId=arr[1]; 
            break; 
        } 
    } 
    alert(userId); 
</script>
//设置过期时间
<script language="JavaScript" type="text/javascript"> 
    //获取当前时间 
    var date=new Date(); 
    var expiresDays=10; 
    //将date设置为10天以后的时间 
    date.setTime(date.getTime()+expiresDays*24*3600*1000); 
    //将userId和userName两个cookie设置为10天后过期 
    document.cookie="userId=828; userName=hulk; expires="+date.toGMTString(); 
</script>
<script language="JavaScript" type="text/javascript"> 
    //获取当前时间 
    var date=new Date(); 
    //将date设置为过去的时间 
    date.setTime(date.getTime()-10000); 
    //将userId这个cookie删除 
    document.cookie="userId=828; expires="+date.toGMTString(); 
</script>
```

常用的HTTP动词有下面五个（括号里是对应的SQL命令）。

> * GET（SELECT）：从服务器取出资源（一项或多项）。
> * POST（CREATE）：在服务器新建一个资源。
> * PUT（UPDATE）：在服务器更新资源（客户端提供改变后的完整资源）。
> * PATCH（UPDATE）：在服务器更新资源（客户端提供改变的属性）。
> * DELETE（DELETE）：从服务器删除资源。

还有两个不常用的HTTP动词。

> * HEAD：获取资源的元数据。
> * OPTIONS：获取信息，关于资源的哪些属性是客户端可以改变的。

https和http的主要区别：

一、https协议需要到ca机构申请ssl证书。

二、http是超文本传输协议，信息是明文传输，https 则是具有安全性的ssl加密传输协议。

三、http和https使用的是完全不同的连接方式，用的端口也不一样，http是80端口，https是443端口。

四、http的连接很简单，是无状态的;https协议是由ssl+http协议构建的可进行加密传输、身份认证的网络协议，比http协议安全。

