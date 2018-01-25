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

