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
arr.push('我的1')     //将一个或多个新元素添加到数组结尾，并返回数组新长度
arr.unshift('我的2')      //将一个或多个新元素添加到数组开始，数组中的元素自动后移，返回数组新长度
arr.splice('')     //将一个或多个新元素插入到数组的指定位置，插入位置的元素自动后移，返回""。
//数组删除元素
arr.pop()   //删除并返回最后一个元素
arr.shift();  //删除并返回第一个元素
arr.splice();   //删除指定元素，并返回删除的元素
//数组的截取和合并
slice(start,[end]) 方法可从已有的数组中返回选定的元素。
```

arr.splice\(\)的用法   向/从数组中添加/删除项目，然后返回被删除的项目。改变原数组

第一个参数是索引，第二个参数是删除几个，第三个参数是用什么代替。

```
(1)添加元素
arr.splice(2,0,"William")   //索引为2
George,John,Thomas,James,Adrew,Martin
George,John,William,Thomas,James,Adrew,Martin
(2)删除位于 index 2 的元素，并添加一个新元素来替代被删除的元素
arr.splice(2,1,"William")
George,John,Thomas,James,Adrew,Martin
George,John,William,James,Adrew,Martin
(3)删除从 index 2 ("Thomas") 开始的三个元素，并添加一个新元素 ("William") 来替代被删除的元素
George,John,Thomas,James,Adrew,Martin
George,John,William,Martin
```



