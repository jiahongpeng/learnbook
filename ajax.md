原生：

//原生js写ajax就像打电话

//打电话分下面4步  
//1.拿出手机  
//2.拨号  
//3.说话  
//4.挺对方说话

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
                    alert("成功"+oAjax.responseText);//读取a.txt文件成功就弹出成功。后面加上oAjax.responseText会输出a.txt文本的内容
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



