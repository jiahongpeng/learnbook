JSON 是用于存储和传输数据的格式。

JSON 通常用于服务端向网页传递数据 。

```
{"sites":[
    {"name":"Runoob","url":"www.runoob.com"},
    {"name":"Google","url":"www.google.com"},
    {"name":"Taobao","url":"www.taobao.com"}
]}
var text = '{ "sites" : [' +
    '{ "name":"Runoob" , "url":"www.runoob.com" },' +
    '{ "name":"Google" , "url":"www.google.com" },' +
    '{ "name":"Taobao" , "url":"www.taobao.com" } ]}';

obj = JSON.parse(text);
```

JSON.parse（）：字符串转化成json对象；

JSON.stringify（）：JSON对象转化成字符串；

html.join\(''\)：join\(\) 方法用于把**数组**中的所有元素放入一个字符串；

push\(\):把元素放入数组；

数组操作方法：

```
var arr=new Array();
//访问数组
var a=arr[0];
//添加新元素
arr[0]='我的';
//数组元素的添加
arr.push('我的')     //将一个或多个新元素添加到数组结尾，并返回数组新长度
arr.unshift()      //将一个或多个新元素添加到数组开始，数组中的元素自动后移，返回数组新长度
```



