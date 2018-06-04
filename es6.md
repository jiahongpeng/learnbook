**let和var的区别？**

（1）let命令所在的代码块内有效，

JavaScript 引擎内部会记住上一轮循环的值，初始化本轮的变量 i 时，就在上一轮循环的基础上进行计算。

解决闭包（for）

（2）不存在变量提升

如果变量没有声明，则报错

（3）暂时性死区（由于（2）造成的），只能在声明的位置后面使用。

（4）不允许重复声明

**es6中声明变量的方式**

`var`命令和`function`命令  `let`和`const`命令  `import`命令和`class`命令

**变量的解构赋值**

（1）交换变量的值

```
let x = 1;
let y = 2;
[x, y] = [y, x];
```

（2）从函数返回多个值

```
// 返回一个数组

function example() {
  return [1, 2, 3];
}
let [a, b, c] = example();

// 返回一个对象

function example() {
  return {
    foo: 1,
    bar: 2
  };
}
let { foo, bar } = example();
```

（3）函数参数的定义

```
// 参数是一组有次序的值
function f([x, y, z]) { ... }
f([1, 2, 3]);

// 参数是一组无次序的值
function f({x, y, z}) { ... }
f({z: 3, y: 2, x: 1});
```

（4）提取 JSON 数据

```
let jsonData = {
  id: 42,
  status: "OK",
  data: [867, 5309]
};

let { id, status, data: number } = jsonData;

console.log(id, status, number);
// 42, "OK", [867, 5309]
```

（5）函数参数的默认值

```
jQuery.ajax = function (url, {
  async = true,
  beforeSend = function () {},
  cache = true,
  complete = function () {},
  crossDomain = false,
  global = true,
  // ... more config
} = {}) {
  // ... do stuff
};
```



