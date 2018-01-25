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

