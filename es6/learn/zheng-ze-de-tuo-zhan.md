1.RegExp\(\)构造函数

```
//es5
var regex = new RegExp(/xyz/);

//es6
var regex = new RegExp(/xyz/, 'i');

//指定新的修饰符，原有正则对象的修饰符是ig，它会被第二个参数i覆盖
new RegExp(/abc/ig, 'i').flags
// "i"
```



