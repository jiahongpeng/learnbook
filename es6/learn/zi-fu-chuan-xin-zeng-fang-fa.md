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

//0-1相当于0，nan也相当于0
'na'.repeat(-0.9) // ""
'na'.repeat(NaN) // ""
'na'.repeat(undefined) // ""


'na'.repeat('na') // ""
'na'.repeat('3') // "nanana"
```

7.实例方法

padStart\(\)：头部补全

padEnd\(\)：尾部补全

```
'x'.padStart(5, 'ab') // 'ababx'
'x'.padStart(4, 'ab') // 'abax'

'x'.padEnd(5, 'ab') // 'xabab'
'x'.padEnd(4, 'ab') // 'xaba'


//长度小于原来字符串长度，则不变
'xxx'.padStart(2, 'ab') // 'xxx'
'xxx'.padEnd(2, 'ab') // 'xxx'

//如果补全后的字符串和比需要的长度长，则自动截取
'abc'.padStart(10, '0123456789')

//第二个参数没有，用空格补全
'x'.padStart(4) // '   x'
'x'.padEnd(4) // 'x   '

//提示字符串格式
'12'.padStart(10, 'YYYY-MM-DD') // "YYYY-MM-12"
'09-12'.padStart(10, 'YYYY-MM-DD') // "YYYY-09-12"
```

8.实例方法：

trimStart\(\):去掉头部空格

trimEnd\(\)：去掉尾部空格

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***以上方法都不改变原字符串\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

