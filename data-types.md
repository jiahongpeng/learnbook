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
//1. 最简单数组去重法 
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
//2. 速度最快， 占空间最多（空间换时间） 
function unique2(array){
    var n = {}, r = [], len = array.length, val, type; 
    for (var i = 0; i < array.length; i++) { 
        val = array[i]; 
        type = typeof val; 
        if (!n[val]) { 
            n[val] = [type]; 
            r.push(val); 
        } else if (n[val].indexOf(type) < 0) { 
            n[val].push(type); 
            r.push(val); 
        } 
    } 
    return r;
}
//3.如果当前数组的第i项在当前数组中第一次出现的位置不是i，那么表示第i项是重复的，忽略掉。否则存入结果数组。
function unique3(array){
    var n = [array[0]]; //结果数组
    //从第二项开始遍历 
    for(var i = 1; i < array.length; i++) { 
        //如果当前数组的第i项在当前数组中第一次出现的位置不是i， 
        //那么表示第i项是重复的，忽略掉。否则存入结果数组 
        if (array.indexOf(array[i]) == i) n.push(array[i]);
    }
    return n; 
}
// 4.将相同的值相邻，然后遍历去除重复值 
function unique4(array){ 
    array.sort(); 
    var re=[array[0]]; 
    for(var i = 1; i < array.length; i++){ 
        if( array[i] !== re[re.length-1]){ 
              re.push(array[i]); 
        }
    }
    return re;
}
// 5.思路：获取没重复的最右一值放入新数组 
function unique5(array){ 
    var r = []; 
    for(var i = 0, l = array.length; i < l; i++) { 
        for(var j = i + 1; j < l; j++) {
            if (array[i] === array[j]) j = ++i; 
        }
        r.push(array[i]); 
    } 
    return r; 
}
//利用Array.from将Set结构转换成数组
function dedupe(array){
 return Array.from(new Set(array));
}
dedupe([1,1,2,3]) //[1,2,3]
//拓展运算符(...)内部使用for...of循环
let arr = [1,2,3,3];
let resultarr = [...new Set(arr)]; 
console.log(resultarr); //[1,2,3]
```



