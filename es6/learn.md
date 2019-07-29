1.数组结构赋值（从数组中提取值）

（1）基本用法

等号右面必须是数组

```
let [a, b, c] = [1, 2, 3];

let [head, ...tail] = [1, 2, 3, 4];
head // 1
tail // [2, 3, 4]

let [x, y, ...z] = ['a'];
x // "a"
y // undefined
z // []

let [x, y, z] = new Set(['a', 'b', 'c']);
x // "a"
```

（2）默认值

```
let [foo = true] = [];
foo // true

let [x, y = 'b'] = ['a']; // x='a', y='b'
let [x, y = 'b'] = ['a', undefined]; // x='a', y='b'

//只有当一个数组成员严格等于undefined，默认值才会生效
let [x = 1] = [undefined];
x // 1

let [x = 1] = [null];
x // null


//默认值可以引用解构赋值的其他变量，但该变量必须已经声明。
let [x = 1, y = x] = [];     // x=1; y=1
let [x = 1, y = x] = [2];    // x=2; y=2
let [x = 1, y = x] = [1, 2]; // x=1; y=2
let [x = y, y = 1] = [];     // ReferenceError: y is not defined
```

2.对象的结构赋值

