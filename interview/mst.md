1、javascript的typeof返回哪些数据类型

**答案**：string,boolean,number,undefined,function,object

2、例举3种强制类型转换和2种隐式类型转换

强制：parseInt,parseFloat,number

隐式转换：（==   ===）

3、split\(\) join\(\)的区别

split\(\)是字符串转数组，join\(\)数组转字符串

4、数组方法pop\(\) push\(\) unshift\(\) shift\(\)

push\(\)尾部添加，pop\(\)尾部删除，unshift\(\)头部添加，shift\(\)头部删除

添加返回的是数组长度，删除返回的是删除元素，不能传参，只能删除一个

5、ajax请求的时候get和post方式的区别

一个在url后面，一个放在虚拟载体里面

get有大小限制\(只能提交少量参数\)

应用不同，请求数据和提交数据

6、call、apply、bind的区别

```
//基本用法
function add(a,b){
  return a+b;  
}
function sub(a,b){
  return a-b;  
}
var a1 = add.apply(sub,[4,2]);　　//sub调用add的方法
var a2 = sub.apply(add,[4,2]);
alert(a1);  //6     
alert(a2);  //2

/*call的用法*/
var a1 = add.call(sub,4,2);
//继承
function Animal(name){
  this.name = name;
  this.showName = function(){
        alert(this.name);    
    }    
}

function Cat(name){
  Animal.apply(this,[name]);    
}

var cat = new Cat("咕咕");
cat.showName();

/*call的用法*/
Animal.call(this,name);
//多重继承
function Class10(){
  this.showSub = function(a,b){
        alert(a - b);
    }   
}

function Class11(){
  this.showAdd = function(a,b){
        alert(a + b);
    }  
}

function Class12(){
  Class10.apply(this);
  Class11.apply(this);   
  // Class10.call(this);
  //Class11.call(this);  
}

var c2 = new Class12();
c2.showSub(3,1);    //2
c2.showAdd(3,1);    //4
```





