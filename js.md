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
console.log(result .index);//2
console.log(result.input );//I,love,you,Do,you,love,me

var myStr = "I,love,you,Do,you,love,me";
var pattern = /love/;
var result = pattern .exec(myStr);//["love"]
console.log(result .index);//2
console.log(result.input );//I,love,you,Do,you,love,me

仅返回查到的匹配的下标，如果匹配失败则返回-1.
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



