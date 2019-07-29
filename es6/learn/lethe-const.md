1.let

（1）不存在变量提升

（2）暂时性死区：在代码块内，使用`let`命令声明变量之前，该变量都是不可用的。这在语法上，称为“暂时性死区”

如果区块中存在`let`和`const`命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。

（3）不允许重复声明：let不允许在相同作用域内，重复声明同一个变量。

2.块级作用域

（1）声明不会提前

3.const

（1）声明一个只读的常量。一旦声明，常量的值就不能改变

（2）一旦声明，必须赋值

（3）

```
const a = [];
a.push('Hello'); // 可执行
a.length = 0;    // 可执行
a = ['Dave'];    // 报错
const foo = Object.freeze({});
// 常规模式时，下面一行不起作用；
// 严格模式时，该行会报错
foo.prop=123;



//属性冻结
var constantize = (obj) => {
  Object.freeze(obj);
  Object.keys(obj).forEach( (key, i) => {
    if ( typeof obj[key] === 'object' ) {
      constantize( obj[key] );
    }
  });
};
```



