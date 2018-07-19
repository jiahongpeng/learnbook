1.**what will happen after I input an url in a browser and hit enter?\*\*\*\*\*\*\***

第一步：客户机提出域名解析请求,并将该请求发送给本地的域名服务器。\(网址到IP地址的转换\)

第二步：当本地的域名服务器收到请求后,就先查询本地的缓存\(本地域名服务器，chrome://dns/\),如果有该纪录项,则本地的域名服务器就直接把查询的结果返回。

第三步：如果本地的缓存中没有该纪录,则本地域名服务器就直接把请求发给根域名服务器,然后根域名服务器再返回给本地域名服务器一个所查询域\(根的子域\)的主域名服务器的地址。

第四步：本地服务器再向上一步返回的域名服务器发送请求,然后接受请求的服务器查询自己的缓存,如果没有该纪录,则返回相关的下级的域名服务器的地址。

第五步：重复第四步,直到找到正确的纪录。

![](/assets/1618288278-57f00bf9444dd_articlex.png)

[https://www.cnblogs.com/engeng/articles/5943382.html](https://www.cnblogs.com/engeng/articles/5943382.html)

a. 域名解析

b. 发起TCP的3次握手（4次挥手是关闭）

c. 建立TCP连接后发起http请求

HTTP报文是包裹在TCP报文中发送的，服务器端收到TCP报文时会解包提取出HTTP报文。但是这个过程中存在一定的风险，HTTP报文是明文，如果中间被截取的话会存在一些信息泄露的风险。那么在进入TCP报文之前对HTTP做一次加密就可以解决这个问题了。HTTPS协议的本质就是HTTP + SSL\(or TLS\)。在HTTP报文进入TCP报文之前，先使用SSL对HTTP报文进行加密。从网络的层级结构看它位于HTTP协议与TCP协议之间。

HTTPS相比于HTTP，虽然提供了安全保证，但是势必会带来一些时间上的损耗，如握手和加密等过程

![](/assets/3598916885-5608f6c220945_articlex.png)

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

作用：改变this的指向

this的指向在函数创建的时候是决定不了的，在调用的时候才能决定，谁调用的就指向谁

```
function Fn(){
    this.user = "追梦子";
}
var a = new Fn();    //改变this指向 为什么this会指向a？首先new关键字会创建一个空的对象，然后会自动调用一个函数apply（打比方）
方法，将this指向这个空对象，这样的话函数内部的this就会被这个空的对象替代。
console.log(a.user); //追梦子

//如果返回值是对象，则this指向的是返回的对象，如果不是对象，this指向该函数的实例
//对象
function fn()  
{  
    this.user = '追梦子';  
    return {};  
}
var a = new fn;  
console.log(a.user); //undefined
//不是对象
function fn()  
{  
    this.user = '追梦子';  
    return 1;
}
var a = new fn;  
console.log(a.user); //追梦子
```

**call和apply的区别就是，apply第二个参数必须是一个数组**

注意如果call和apply的第一个参数写的是null和defined，那么this指向的是window对象

```
var a = {
    user:"追梦子",
    fn:function(e,ee){
        console.log(this.user); //追梦子
        console.log(e+ee); //11
    }
}
var b = a.fn;
b.apply(a,[10,1]);
b.call(a,10,1);
//bind
var a = {
    user:"追梦子",
    fn:function(){
        console.log(this.user); //追梦子
    }
}
var b = a.fn;
var c = b.bind(a);
c();
```

**call和apply都是改变上下文中的this并立即执行这个函数，bind方法可以让对应的函数想什么时候调就什么时候调用，并且可以将参数在执行的时候添加。（bind的第二个参数也可以是数组）**

[https://www.jianshu.com/p/c9139b1da603（看不懂）](https://www.jianshu.com/p/c9139b1da603（看不懂）)

8.深拷贝与浅拷贝

[https://blog.csdn.net/u014628388/article/details/77489400](https://blog.csdn.net/u014628388/article/details/77489400)

[https://blog.csdn.net/mafan121/article/details/74420957](https://blog.csdn.net/mafan121/article/details/74420957)（完美）

**浅复制**—只是拷贝了基本类型的数据，而引用类型数据，复制后也是会发生引用，我们把这种拷贝叫做“（浅复制）浅拷贝”，换句话说，浅复制仅仅是指向被复制的内存地址，如果原地址中对象被改变了，那么浅复制出来的对象也会相应改变。（反之如此）

**深复制**—在计算机中开辟了一块新的内存地址用于存放复制的对象。

深复制——递归函数

```
function myFun(n){
    if(n == 1){
        return 1;
    }       
    return n*myFun(n-1);    
}
alert("5的阶乘为："+myFun(5));
```

箭头函数：this指向调用的对象。不能用call，bind，apply

会被转化成false的值：false

```
undefined
null
0
-0
NaN
""
''
```

几种判断类型的方法

（1）typeof

```
undefined：undefined
object:object
array:object
null:object
string:string
number:number
boolean:boolean
```

（2）instanceof

```
u instanceof Person（结果是boolean）
```

（3）constructor

```
Object.constructor
```

方法一：（value是function不可以）

var obj2=JSON.parse\(JSON.stringify\(obj1\)\)    

方法二\(递归\)：

```
const isType=(a)=>{
    if(a===undefined){
        return "umdefined";    
    }else if(a===null){
        return "null";
    }else{
        return Object.prototype.toString.call(a).slice(8,-1)
    }
}
const deepClone=(b)=>{
    if(!b){return null};
    let result,oClass=isType(b);
    if(oClass==="Object"){
        result={};
    }else if(oClass==="Array"){
        result=[];
    }else{
        return b;
    };
    for(let key in b){
        if(b.hasOwnProperty(key)){
            let ccopy=b[key];
            if(isType(ccopy)==="Object"){
                result[key]=deepClone(ccopy);
            }else if(isType(ccopy)==="Array"){
                result[key]=deepClone(ccopy);
            }else{
                result[key]=ccopy;
            }
        }
    }
    return result;
}
let obj={a:1,b:[2,3]}
var res=deepClone(obj);
console.log(res);
```

[https://segmentfault.com/a/1190000007535316](https://segmentfault.com/a/1190000007535316)

1. 获取url参数

```
getQueryData: function (queryString) {
    var arr = queryString.split("?");
    var querys = arr[1].split('&'),i = 0,parms = {},item;
    while (i < querys.length) {
        item = querys[i].split('=');
        if (item[0]) {
            var value = item[1] || '';
            value = (value === 'null') ? null : value;
            parms[item[0]] = decodeURIComponent(value);
        }
        i++;
    }
    return parms;
}
```



