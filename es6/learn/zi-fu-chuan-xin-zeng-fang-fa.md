5.实例方法

使用第二个参数

`n`

时，

`endsWith`

的行为与其他两个方法有所不同。它针对前

`n`

个字符，而其他两个方法针对从第

`n`

个位置直到字符串结束。

```
let s = 'Hello world!';

s.startsWith('world', 6) // true
s.endsWith('Hello', 5) // true
s.includes('Hello', 6) // false
```

6.repeat

