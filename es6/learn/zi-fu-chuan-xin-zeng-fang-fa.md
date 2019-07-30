5.实例方法

```
//使用第二个参数n时，endsWith的行为与其他两个方法有所不同。它针对前n个字符，而其他两个方法针对从第n个位置直到字符串结束。
let s = 'Hello world!';

s.startsWith('world', 6) // true
s.endsWith('Hello', 5) // true
s.includes('Hello', 6) // false
```

6.实例方法：repeat\(\)

```
'x'.repeat(3) // "xxx"
'hello'.repeat(2) // "hellohello"
'na'.repeat(0) // ""
//小数取整
'na'.repeat(2.9) // "nana"

'na'.repeat(Infinity)
// RangeError
'na'.repeat(-1)
// RangeError

'na'.repeat(-0.9) // ""
```



