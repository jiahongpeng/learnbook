JSON 是用于存储和传输数据的格式。

JSON 通常用于服务端向网页传递数据 。

```
{"sites":[
    {"name":"Runoob","url":"www.runoob.com"},
    {"name":"Google","url":"www.google.com"},
    {"name":"Taobao","url":"www.taobao.com"}
]}
var text = '{ "sites" : [' +
    '{ "name":"Runoob" , "url":"www.runoob.com" },' +
    '{ "name":"Google" , "url":"www.google.com" },' +
    '{ "name":"Taobao" , "url":"www.taobao.com" } ]}';

obj = JSON.parse(text);
```

JSON.parse（）：字符串转化成json对象；

JSON.stringify（）：JSON对象转化成字符串；

html.join\(''\)：join\(\) 方法用于把**数组**中的所有元素放入一个字符串；

push\(\):把元素放入数组；

数组操作方法：

```
var arr=new Array();
//访问数组
var a=arr[0];
//添加新元素
arr[0]='我的';
//数组元素的添加
arr.push('我的1')     //将一个或多个新元素添加到数组结尾，并返回数组新长度
arr.unshift('我的2')      //将一个或多个新元素添加到数组开始，数组中的元素自动后移，返回数组新长度
arr.splice('')     //将一个或多个新元素插入到数组的指定位置，插入位置的元素自动后移，返回""。
//数组删除元素
arr.pop()   //删除并返回最后一个元素
arr.shift();  //删除并返回第一个元素
arr.splice();   //删除指定元素，并返回删除的元素
//数组的截取和合并
arr.slice(start,[end]) 方法可从已有的数组中返回选定的元素，不包含end的值。不改变原数组
concat() 方法用于连接两个或多个数组。arr.concat(arr2,arr3)  返回最新的数组
//数组的拷贝
arr.slice(0)   //返回数组的拷贝数组，注意是一个新的数组
arr.concat()   //返回数组的拷贝数组，注意是一个新的数组
//数组元素的排序
arr.reverse(); //反转元素（最前的排到最后、最后的排到最前），返回数组地址
arr.sort(); //对数组元素排序，返回数组地址
//数组元素的字符串化
arr.join('元素分隔符'); //返回字符串，这个字符串将数组的每一个元素值连接在一起，中间用 separator 隔开，如果join()就默认 ， 不改变原数组

//搜索指定元素的位置
arr.indexOf():搜索指定元素的位置，indexOf()方法返回在该数组中第一个找到的元素位置，如果它不存在则返回-1。
```

arr.splice\(\)的用法   向/从数组中添加/删除项目，然后返回被删除的项目。改变原数组

第一个参数是索引，第二个参数是删除几个，第三个参数是用什么代替。

```
(1)添加元素
arr.splice(2,0,"William")   //索引为2
George,John,Thomas,James,Adrew,Martin
George,John,William,Thomas,James,Adrew,Martin
(2)删除位于 index 2 的元素，并添加一个新元素来替代被删除的元素
arr.splice(2,1,"William")
George,John,Thomas,James,Adrew,Martin
George,John,William,James,Adrew,Martin
(3)删除从 index 2 ("Thomas") 开始的三个元素，并添加一个新元素 ("William") 来替代被删除的元素
George,John,Thomas,James,Adrew,Martin
George,John,William,Martin
```

sort（）的用法，改变的是原来的数组

```
//比较大小：从小到大
var arr=[0,20,1,2];
arr.sort(function(x,y){
    if(x<y){
        return -1
    }else if(x>y){
        return 1
    }else{
        return 0
    }
})
*****当x>y时，返回1，则交换a和b的位置（小的在前面），一直到全部都返回1*********
```

```
var arr = [
        {"name":"apple", "count": 2},
        {"name":"orange", "count": 5},
        {"name":"pear", "count": 3},
        {"name":"orange", "count": 16},
];        
var newArr = arr.filter(function(item){
        return item.name === "orange";
});
console.log("Filter results:",newArr);
结果：[0:{name: "orange", count: 5},
      1:{name: "orange", count: 16}]


循环
var arr = [1,2,3,4,5,6,7,8];
// Uses the usual "for" loop to iterate
for(var i= 0, l = arr.length; i< l; i++){
console.log(arr[i]);
}

console.log("========================");

//Uses forEach to iterate
arr.forEach(function(item,index){
console.log(item);
});
```



