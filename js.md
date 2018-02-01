字符串操作

1.字符串转换

num.toString\(\)，num.string\(\)

2.字符串分割

```
var myStr = "I,Love,You,Do,you,love,me";
mystr.split(',');   // ["I", "Love", "You", "Do", "you", "love", "me"];   
var arrayLimited = myStr .split(",", 3); // ["I", "Love", "You"];  //返回字符串的长度
```

3.获取字符串长度

```
var myStr = "I,Love,You,Do,you,love,me";
mystr.length;   //25
```

4.查询子字符串

```
var myStr = "I,Love,You,Do,you,love,me";
var index = myStr.indexOf("you"); // 7 ,基于0开始,找不到返回-1
varmyStr ="I,Love,you,Do,you,love,me";
var index = myStr.lastIndexOf("you");// 14  从末尾开始查找，找到返回对应坐标，找不到返回-1
```

5.字符串替换

替换第一个

`var myStr = "I,love,you,Do,you,love,me";var replacedStr = myStr.replace("love","hate");//"I,hate,you,Do,you,love,me"`

全局

`var myStr ="I,love,you,Do,you,love,me";var replacedStr = myStr.replace(/love/g,"hate");//"I,hate,you,Do,you,hate,me"`

6.查找给定位置的字符或其字符编码值

```
var myStr = "I,Love,You,Do,you,love,me";
myStr.charAt(8);   //o
//查找对应位置的字符编码值
var myStr = "I,love,you,Do,you,love,me";
var theChar = myStr.charCodeAt(8); //111
```

7.字符串连接

```
var str1 = "I,love,you!";
var str2 = "Do,you,love,me?";
var str = str1 + str2 + "Yes!";//"I,love,you!Do,you,love,me?Yes!"

var str1 = "I,love,you!";
var str2 = "Do,you,love,me?";
var str = str1.concat(str2);//"I,love,you!Do,you,love,me?"
```

8.字符串切割和提取

`var myStr ="I,love,you,Do,you,love,me";varsubStr = myStr.slice(1,5);//",lov"从1到5`

`var myStr ="I,love,you,Do,you,love,me";varsubStr = myStr.substring(1,5);//",lov" 从1到5`

`var myStr ="I,love,you,Do,you,love,me";varsubStr = myStr.substr(1,5);//",lov" 从1开始，一共5个`

9.字符串大小写转换

```
var myStr = "I,Love,You,Do,you,love,me";
var lowCaseStr = myStr.toLowerCase();//"i,love,you,do,you,love,me";
var upCaseStr = myStr.toUpperCase();//"I,LOVE,YOU,DO,YOU,LOVE,ME"
```

10.字符串比较

```
var myStr = "chicken";
var myStrTwo = "egg";
var first = myStr.localeCompare(myStrTwo); // -1
first = myStr.localeCompare("chicken"); // 0
first = myStr.localeCompare("apple"); // 1
```

11.字符串匹配（正则表达式）

```
//匹配的结果都是返回第一个匹配成功的字符串，如果匹配失败则返回null.
var myStr = "chicken";
var myStr = "I,love,you,Do,you,love,me";
var pattern = /love/;
var result = myStr.match(pattern);//["love"]
console.log(result.index);//2
console.log(result.input );//I,love,you,Do,you,love,me

var myStr = "I,love,you,Do,you,love,me";
var pattern = /love/;
var result = pattern .exec(myStr);//["love"]
console.log(result.index);//2
console.log(result.input );//I,love,you,Do,you,love,me

//仅返回查到的匹配的下标，如果匹配失败则返回-1.
var myStr = "I,love,you,Do,you,love,me";
var pattern = /love/;
var result = myStr.search(pattern);//2
```

12.总结

```
var myStr = "chicken";
function getSuffix(file){return
file.slice(file.lastIndexOf(".") + 1,file.length);}
```

13.字符串去重

```
//String.split() 执行的操作与 Array.join 执行的操作是相反的 
//split() 方法用于把一个字符串分割成字符串数组。 
//join方法用于将字符串数组连接成一个字符串 
//如果把空字符串 ("") 用作 separator，那么 stringObject 中的每个字符之间都会被分割。 
var str="aahhgggsssjjj";//这里字符串没有可以分隔的字符，所以需要使用空字符串作为分隔符 
    function unique(msg){ 
      var res=[]; 
      var arr=msg.split(""); 
      //console.log(arr); 
      for(var i=0;i<arr.length;i++){ 
        if(res.indexOf(arr[i])==-1){ 
          res.push(arr[i]); 
        } 
      } 
    return res.join(""); 
} 
console.log(unique(str));//ahgsj
```

14.正则表达式

\s：空格

\d：数字   \[0-9\]

{3,9}：3到9位

^\d  :以数字结尾

\d$：以数字结尾

/g：全局搜索

\[a-zA-Z\]   \w

\*：匹配前面的子表达式零次或多次。例如，zo\*能匹配“`z`”以及“`zoo`”。\*等价于{0,}。

+： 匹配前面的子表达式一次或多次。例如，“`zo+`”能匹配“`zo`”以及“`zoo`”，但不能匹配“`z`”。+等价于{1,}。

? :  匹配前面的子表达式零次或一次。例如，“`do(es)?`”可以匹配“`does`”或“`does`”中的“`do`”。?等价于{0,1}。

? : 当该字符紧跟在任何一个其他限制符（\*,+,?，{n}，{n,}，{n,m}）后面时，匹配模式是非贪婪的。非贪婪模式尽可能少的匹配所搜索的字符串，而默认的贪婪模式则尽可能多的匹配所搜索的字符串。例如，对于字符串“`oooo`”，“`o+?`”将匹配单个“`o`”，而“`o+`”将匹配所有“`o`”。

1，/g 表示该表达式将用来在输入字符串中查找所有可能的匹配，返回的结果可以是多个。如果不加/g最多只会匹配一个

2，/i  表示匹配的时候不区分大小写

3，/m 表示多行匹配

[http://tool.oschina.net/uploads/apidocs/jquery/regexp.html](http://tool.oschina.net/uploads/apidocs/jquery/regexp.html)

15.时间操作

```
var myDate = new Date();
myDate.getYear();        //获取当前年份(2位)
myDate.getFullYear();    //获取完整的年份(4位,1970-????)
myDate.getMonth();       //获取当前月份(0-11,0代表1月)
myDate.getDate();        //获取当前日(1-31)
myDate.getDay();         //获取当前星期X(0-6,0代表星期天)
myDate.getTime();        //获取当前时间(从1970.1.1开始的毫秒数)
myDate.getHours();       //获取当前小时数(0-23)
myDate.getMinutes();     //获取当前分钟数(0-59)
myDate.getSeconds();     //获取当前秒数(0-59)
myDate.getMilliseconds();    //获取当前毫秒数(0-999)
myDate.toLocaleDateString();     //获取当前日期
var mytime=myDate.toLocaleTimeString();     //获取当前时间
myDate.toLocaleString( );        //获取日期与时间
Date.parse()              //换算当前时间的毫秒数
//在某一时间段显示广告
var timestart = '2015-09-05'; 
var timeend = '2015-09-06';
var time1 = (timestart+' 16:00:00').toString(); 
var time2 = (timeend+' 16:00:00').toString(); 
timestart = new Date(Date.parse(time1.replace(/-/g,"/"))).getTime(); 
timeend = new Date(Date.parse(time2.replace(/-/g,"/"))).getTime();
var nowtime=new Date().getTime();
if (nowtime>timestart && nowtime<timeend)
{
    document.write("广告");
}

//时间转化成2005-08-05
var strDate = '2005-8-5'; 
window.alert(strDate.replace(/\b(\w)\b/g, '0$1'));
//间隔天数
alert("间隔天数为:"+(new Date('2005/8/15')-new Date('2003/9/18'))/1000/60/60/24+"天")
//间隔时分秒
var d1=new Date("2004/09/16 20:08:00"); 
var d2=new Date("2004/09/16 10:18:03"); 
var d3=d1-d2; 
var h=Math.floor(d3/3600000);
var m=Math.floor((d3-h*3600000)/60000); 
var s=(d3-h*3600000-m*60000)/1000;
alert("相差"+h+"小时"+m+"分"+s+"秒");
//得到今天的日期
d = new Date(); 
alert(d.getFullYear()+"年"+(d.getMonth()+1)+"月"+d.getDate()+"日");
```

form表单：

```
<form id="test-register" action="#" target="_blank" onsubmit="return checkRegisterForm()">
    <p id="test-error" style="color:red"></p>
    <p>
        用户名: <input type="text" id="username" name="username">
    </p>
    <p>
        口令: <input type="password" id="password" name="password">
    </p>
    <p>
        重复口令: <input type="password" id="password-2">
    </p>
    <p>
        <button type="submit">提交</button> <button type="reset">重置</button>
    </p>

    //md加密
    <input type="hidden" id="md5-password" name="password">
    md5_pwd.value = toMD5(input_pwd.value);
</form>
<script>
    var name = document.getElementById('username').value;
    var pwd1 = document.getElementById('password').value;
    var pwd2 = document.getElementById('password-2').value;
    if (/^[\w\d]{3,10}$/.test(name) === false) {
        alert("用户名格式错误");
        return false;
    }

    if (pwd1 === pwd2 && pwd1.length < 12 && pwd1.length > 6) {
        alert("成功");
        return true;
    }
    alert("密码格式错误");
    return false;
    }
</script>
```

上传图片

```
var fileInput = document.getElementById('test-image-file'),
    info = document.getElementById('test-file-info'),
    preview = document.getElementById('test-image-preview');
// 监听change事件:
fileInput.addEventListener('change', function () {
    // 清除背景图片:
    preview.style.backgroundImage = '';
    // 检查文件是否选择:
    if (!fileInput.value) {
        info.innerHTML = '没有选择文件';
        return;
    }
    // 获取File引用:
    var file = fileInput.files[0];
    // 获取File信息:
    info.innerHTML = '文件: ' + file.name + '<br>' +
                     '大小: ' + file.size + '<br>' +
                     '修改: ' + file.lastModifiedDate;
    if (file.type !== 'image/jpeg' && file.type !== 'image/png' && file.type !== 'image/gif') {
        alert('不是有效的图片文件!');
        return;
    }
    // 读取文件:
    var reader = new FileReader();
    reader.onload = function(e) {
        var
            data = e.target.result; // 'data:image/jpeg;base64,/9j/4AAQSk...(base64编码)...'            
        preview.style.backgroundImage = 'url(' + data + ')';
    };
    // 以DataURL的形式读取文件:
    reader.readAsDataURL(file);
});
```





