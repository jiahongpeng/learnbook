原生：

//原生js写ajax就像打电话

//打电话分下面4步  
//1.拿出手机  
//2.拨号  
//3.说话  
//4.听对方说话

//ajax也分下面4步  
//1.创建ajax对象  
//2.连接到服务器  
//3.发送请求（告诉服务器我要什么文件）  
//4.接收返回值

```js
<script>
window.onload=function(){
    var oBtn = document.getElementById("btn1");
    oBtn.onclick = function(){
        //1.创建ajax对象
        //只兼容非ie6的浏览器，在ie6浏览器上运行会提示没有被定义
        //var oAjax = new XMLHttpRequest();//这才是ajax实际的请求
        //alert(oAjax);
        //ie6浏览器下按照下面方法写,但是在别的浏览器中不能用，会报错。
        //var oAjax = new ActiveXObject("Microsoft.XMLHTTP");
        //alert(oAjax);
        //鉴于上面出现的问题，可以采取下面的方法解决，用if判断是否为IE6浏览器
        if(window.XMLHttpRequest){//如果有XMLHttpRequest，那就是非IE6浏览器。()里面加window的原因下面会有描述。
            var oAjax = new XMLHttpRequest();//创建ajax对象
        }else{//如果没有XMLHttpRequest，那就是IE6浏览器
            var oAjax = new ActiveXObject("Microsoft.XMLHTTP");//IE6浏览器创建ajax对象
        }
        //2.连接服务器
        //open(方法、文件名、异步传输）
        //方法：
        //传输方式是get方式还是post方式。
        //文件名
        //告诉服务器要读哪个文件
        //异步传输
        //异步：多件事一件一件的做
        //同步：多件事情一起进行
        //但是js里面的同步和异步和现实的同步异步相反。
        //同步：多件事一件一件的做
        //异步：多件事情一起进行
        //ajax天生是用来做异步的
        oAjax.open("GET","a.txt?t='+new Date().getTime()",true);//加上t='+new Date().getTime()"的目的是为了消除缓存，每次的t的值不一样。
        //3.发送请求
        oAjax.send();
        //4.接收返回
        //客户端和服务器端有交互的时候会调用onreadystatechange
        oAjax.onreadystatechange=function()
        {
            //oAjax.readyState  //浏览器和服务器，进行到哪一步了。
                //0->（未初始化）：还没有调用 open() 方法。
                //1->（载入）：已调用 send() 方法，正在发送请求。
                //2->载入完成）：send() 方法完成，已收到全部响应内容。
                //3->（解析）：正在解析响应内容。
                //4->（完成）：响应内容解析完成，可以在客户端调用。
            if(oAjax.readyState==4)
            {
                if(oAjax.status==200)//判断是否成功,如果是200，就代表成功
                {
                     /*
                        ** Http状态码
                        ** 1xx ：信息展示
                        ** 2xx ：成功
                        ** 3xx ：重定向
                        ** 4xx : 客户端错误
                        ** 5xx ：服务器端错误
                        */
                    //读取a.txt文件成功就弹出成功。后面加上oAjax.responseText会输出a.txt文本的内容
                    alert("成功"+oAjax.responseText);
                }
                else
                {
                    alert("失败");
                }
            }
        };
    }
};

/*//上面if里面需要些window的原因
//js里面的变量和属性
var a = 12;
alert(a);//页面上弹出12很正常，而实际上输出的是下面的写法，是属于window的，只是window能省就省了。
alert(window.a);//输出结果是一样的
window.alert(window.a);

//想a这种全局变量实际上是winow的一个属性。
//如果不定义一个变量a直接像下面那样输出a
alert(a)//系统会报错，而不是undefind，因为没有定义变量a。
alert(window.a);//如果是这样写，系统就不会报错了，会显示undefind。
//出现上面的原因是因为直接写a从根上就找不到a，而前面加上window只是找不到window的属性a了。*/
</script>


<script>
    function Ajax(type, url, data, success, failed){
        // 创建ajax对象
        var xhr = null;
        if(window.XMLHttpRequest){
            xhr = new XMLHttpRequest();
        } else {
            xhr = new ActiveXObject('Microsoft.XMLHTTP')
        }
        var type = type.toUpperCase();
        // 用于清除缓存
        var random = Math.random();
        if(typeof data == 'object'){
            var str = '';
            for(var key in data){
                str += key+'='+data[key]+'&';
            }
            data = str.replace(/&$/, '');
        }
        if(type == 'GET'){
            if(data){
                xhr.open('GET', url + '?' + data, true);
            } else {
                xhr.open('GET', url + '?t=' + random, true);
            }
            xhr.send();

        } else if(type == 'POST'){
            xhr.open('POST', url, true);
            // 如果需要像 html 表单那样 POST 数据，请使用 setRequestHeader() 来添加 http 头。
            xhr.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
            xhr.send(data);
        }
        // 处理返回数据
        xhr.onreadystatechange = function(){
            if(xhr.readyState == 4){
                if(xhr.status == 200){
                    success(xhr.responseText);
                } else {
                    if(failed){
                        failed(xhr.status);
                    }
                }
            }
        }
    }
    // 测试调用
    var sendData = {name:'asher',sex:'male'};
    Ajax('get', 'data/data.html', sendData, function(data){
        console.log(data);
    }, function(error){
        console.log(error);
    });
</script>
```

JSONP：它有个限制，只能用GET请求。

```
'use strict';
// ajax函数将返回Promise对象:
function ajax(method, url, data) {
    var request = new XMLHttpRequest();
    return new Promise(function (resolve, reject) {
        request.onreadystatechange = function () {
            if (request.readyState === 4) {
                if (request.status === 200) {
                    resolve(request.responseText);
                } else {
                    reject(request.status);
                }
            }
        };
        request.open(method, url);
        request.send(data);
    });
}
var log = document.getElementById('test-promise-ajax-result');
var p = ajax('GET', '/api/categories');
p.then(function (text) { // 如果AJAX成功，获得响应内容
    log.innerText = text;
}).catch(function (status) { // 如果AJAX失败，获得响应代码
    log.innerText = 'ERROR: ' + status;
});
```

get 和 post请求的区别

**GET和POST长度的限制问题**

GET

1.GET是通过URL提交数据，因此GET可提交的数据量就跟URL所能达到的最大长度有直接关系。

2.实际上HTTP协议对URL长度是没有限制的；限制URL长度大多数是浏览器或者服务器的配置参数

POST

1.同样的，HTTP协议没有对POST进行任何限制，一般是受服务器配置限制或者内存大小。

2.PHP下可以修改php.conf的postmaxsize来设置POST的大小。

**请求header的content-length问题**

如果有人恶意伪造content-length很大的包头，但实际上发送content-length很小的请求，这样服务器会一直干等，直到超时。当然服务器是可以通过设置来避免该问题的

**GET和POST的安全性**

1.GET是通过URL方式请求，可以直接看到，明文传输。

2.POST是通过请求header请求，可以开发者工具或者抓包可以看到，同样也是明文的。 

3.GET请求会保存在浏览器历史纪录中，还可能会保存在Web的日志中。

**GET和POST对服务器的状态**

根据http的设计，大家在看到get的时候，都期望这个请求对服务器没有修改，看到post的时候，都认为这对服务器产生了修改。

**GET幂等，POST不幂等**

幂等是指同一个请求方法执行多次和仅执行一次的效果完全相同。

1.按照RFC规范，PUT，DELETE和安全方法都是幂等的。虽说是规范，但服务端实现是否幂等是无法确保的。

2.引入幂等主要是为了处理同一个请求重复发送的情况，比如在请求响应前失去连接，如果方法是幂等的，就可以放心地重发一次请求。这也是浏览器在后退/刷新时遇到POST会给用户提示的原因：POST语义不是幂等的，重复请求可能会带来意想不到的后果。

3.比如在微博这个场景里，GET的语义会被用在「看看我的Timeline上最新的20条微博」这样的场景，而POST的语义会被用在「发微博、评论、点赞」这样的场景中。

**contentType:**

发送信息至服务器时内容编码类型，简单说就是data值\(传参\)的数据类型是什么，默认值是: "application/x-www-form-urlencoded"

但在restful接口中contentType常用到的是：“application/json”，这时候data值的类型只能是字符串，所以要将json对象转成json字符串:

```
var json=JSON.stringify({name:"小明",age:20});
```

**dataType：**

告诉服务器，我想要返回什么类型的数据，就是success方法返回值的类型，除了常见的json、XML，还可以指定 html、jsonp、script或者text

