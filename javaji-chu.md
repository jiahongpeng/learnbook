isNotEmpty\(str\)等价于 str != null && str.length &gt; 0

isNotBlank\(str\) 等价于 str != null && str.length &gt; 0 && str.trim\(\).length &gt; 0

isEmpty 等价于 str == null \|\| str.length == 0

isBlank  等价于 str == null \|\| str.length == 0 \|\| str.trim\(\).length == 0





\| null \| 空字符串\(""\)\|空白字符\(空格、制表符\)\|  
\| isEmpty \| true \| true \| false \|  
\| isNotEmpty \| false \| false \| true \|  
\| isBlank \| true \| true \| true \|  
\| isNotBlank \| false \| false \| false \|

从上表可以看出：  
isNotEmpty\(\) == ! isEmpty\(\)  
isNotBlank\(\) == ! isBlank\(\)

##### isEmpty\(\) 和 isBlank\(\) 对 null 和 空字符串\(""\)的判断相同，唯一区别就是对空白字符（如空格、制表符）的判断。

针对空白字符，isEmpty\(\)返回false，isBlank\(\)返回true.







