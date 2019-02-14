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

相同点：1、都是用来改变函数的this对象的指向的。

```
           2、第一个参数都是this要指向的对象。

           3、都可以利用后续参数传参。
```

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

[https://www.cnblogs.com/cosiray/p/4512969.html](https://www.cnblogs.com/cosiray/p/4512969.html)

**call\(\)和apply\(\)的区别就在于，两者之间的参数。**

call\(\)在第一个参数之后的  后续所有参数就是传入该函数的值。**apply\(\) 只有两个参数**，第一个是对象，第二个是数组，这个数组就是该函数的参数。

bind\(\) 方法和前两者不同在于： bind\(\) 方法会返回执行上下文被改变的函数而不会立即执行，而前两者是直接执行该函数。他的参数和call\(\)相同。

[https://www.jianshu.com/p/bc541afad6ee](https://www.jianshu.com/p/bc541afad6ee)

7、 ajax请求时，如何解析json数据

json.stringfy\(\)将对象、数组转换成字符串；json.parse\(\)将字符串转成json对象。

8、事件委托是什么

利用事件冒泡的原理，让自己的所触发的事件，让他的父元素代替执行！

[https://www.cnblogs.com/jcscript/p/5634439.html](https://www.cnblogs.com/jcscript/p/5634439.html)

```
$(document).on('click','li',function(){
    alert('这是一个li！！！');
});
```

9、闭包是什么，有什么特性，对页面有什么影响

闭包就是能够读取其他函数内部变量的函数,使得函数不被GC回收，如果过多使用闭包，容易导致内存泄露

[https://legacy.gitbook.com/book/jiahongpeng/learnweb-2/edit\#/edit/master/interview/js/bi-bao.md?\_k=59bt8u](https://legacy.gitbook.com/book/jiahongpeng/learnweb-2/edit#/edit/master/interview/js/bi-bao.md?_k=59bt8u)

10、Javascript的事件流模型都有什么?

```
“事件冒泡”：事件开始由最具体的元素接受，然后逐级向上传播

“事件捕捉”：事件由最不具体的节点先接收，然后逐级向下，一直到最具体的

“DOM事件流”：三个阶段：事件捕捉，目标阶段，事件冒泡

https://www.cnblogs.com/jyybeam/p/5794932.html
阻止冒泡  ：event.stopPropagation();



function stopBubble(e){
　　if(e&&e.stopPropagation){//非IE
　　    e.stopPropagation();
　　}
　　else{//IE
　　    window.event.cancelBubble=true;
　　}
}
　　
　　
<a onclick=''>如果要阻止默认事件的触发，即默认的href事件，那么就需要调用如下函数：

function stopDefault( e ) {
　　//阻止默认浏览器动作(W3C)
　　if ( e && e.preventDefault ){
        e.preventDefault();
    }
　　//IE中阻止函数器默认动作的方式
　　else{
        window.event.returnValue = false;
        return false;
    }
}


//option的应用
var click = document.getElementById('inner');
var clickouter = document.getElementById('outer');
click.addEventListener('click',function(event){
    alert('inner show');
    //event.stopPropagation();
},false);//只给inner绑定显示事件
clickouter.addEventListener('click',function(){
    alert('outer show');
},false);
```

11、 ”==”和“===”的不同

```
答案：前者会自动转换类型,再判断是否相等
后者不会自动类型转换，直接去比较
```



