1.string（字符串）

2.number（数字）

3.boolean（布尔）

4.array（存储各种值的结构）

5.object（Everything in JavaScript is an object）

6.null

7.undefined

```
indexOf既能应用在字符串又能应用在数组，arr.indexOf('123'),如果结果是-1，则没有查到。如果查到了，则是下标。
```

**数组去重**

```
// 最简单数组去重法 
function unique1(array){ 
    var n = []; //一个新的临时数组 
    //遍历当前数组 
    for(var i = 0; i < array.length; i++){ 
    //如果当前数组的第i已经保存进了临时数组，那么跳过， 
    //否则把当前项push到临时数组里面 
    if (n.indexOf(array[i]) == -1) n.push(array[i]); 
    } 
    return n; 
}
```



