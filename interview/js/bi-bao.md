一个函数的名称就是这个函数的指针，它只是传递了函数体所在的地址位置，在需要的时候好找到函数体去执行。

```
function a(){
  alert(1);
}
var b=a;
b();   //输出1
var b=a();   //执行a方法，方法a没有返回东西
div.onclick=a;   //点击的时候执行a方法，告诉a方法所在的位置
```

闭包：在函数外部获取不到函数内部的变量。闭包就是能做到这种。闭包就是将函数内部和函数外部连接起来的一座桥梁。

链式作用域"结构：内部函数能获取到外部的，外部获取不到内部的变量。子对象会一级一级地向上寻找所有父对象的变量。所以，父对象的所有变量，对子对象都是可见的，反之则不成立。

```js
functionmakeAdder(x){
    return function(y){
        return x+y;
    };
}
var add5=makeAdder(5);
var add10 =makeAdder(10);
console.log(add5(2));// 7
console.log(add10(2));// 12
```

html:

```
<p id="help">Helpful notes will appear here</p>
<p>E-mail: <input type="text" id="email" name="email"></p>
<p>Name: <input type="text" id="name" name="name"></p>
<p>Age: <input type="text" id="age" name="age"></p>
```

js（没有闭包的时候）

```
function
```

```
function showHelp(help) {
  document.getElementById('help').innerHTML = help;
}

function setupHelp() {
  var helpText = [
      {'id': 'email', 'help': 'Your e-mail address'},
      {'id': 'name', 'help': 'Your full name'},
      {'id': 'age', 'help': 'Your age (you must be over 16)'}
    ];

  for (var i = 0; i < helpText.length; i++) {
    var item = helpText[i];
    document.getElementById(item.id).onfocus = function() {
      showHelp(item.help);
    }
  }
}

setupHelp();
```

js（闭包方法1）

```
function showHelp(help) {
  document.getElementById('help').innerHTML = help;
}

function makeHelpCallback(help) {
  return function() {
    showHelp(help);
  };
}

function setupHelp() {
  var helpText = [
      {'id': 'email', 'help': 'Your e-mail address'},
      {'id': 'name', 'help': 'Your full name'},
      {'id': 'age', 'help': 'Your age (you must be over 16)'}
    ];

  for (var i = 0; i < helpText.length; i++) {
    var item = helpText[i];
    document.getElementById(item.id).onfocus = makeHelpCallback(item.help);
  }
}

setupHelp();
```

js（方法2）

```
function showHelp(help) {
  document.getElementById('help').innerHTML = help;
}

function setupHelp() {
  var helpText = [
      {'id': 'email', 'help': 'Your e-mail address'},
      {'id': 'name', 'help': 'Your full name'},
      {'id': 'age', 'help': 'Your age (you must be over 16)'}
    ];

  for (var i = 0; i < helpText.length; i++) {
    (function() {
       var item = helpText[i];
       document.getElementById(item.id).onfocus = function() {
         showHelp(item.help);
       }
    })(); // Immediate event listener attachment with the current value of item (preserved until iteration).
  }
}

setupHelp();
```

js（闭包方法3）

```
function showHelp(help) {
  document.getElementById('help').innerHTML = help;
}

function setupHelp() {
  var helpText = [
      {'id': 'email', 'help': 'Your e-mail address'},
      {'id': 'name', 'help': 'Your full name'},
      {'id': 'age', 'help': 'Your age (you must be over 16)'}
    ];

  for (var i = 0; i < helpText.length; i++) {
    let item = helpText[i];
    document.getElementById(item.id).onfocus = function() {
      showHelp(item.help);
    }
  }
}

setupHelp();
```

```
var name = "The Window";   
var object = {
    name : "My Object",   
    getNameFunc : function(){   
        return function(){   
            return this.name;   
        };   
    },
    getName:function(){
        alert(this.name);
    }   
};   
alert(object.getNameFunc()());  //The Window
object.getName();  //My Object


//解释
var fn = object.getNameFunc();
fn() // The Window所以this指向全局
```

```
var name = "The Window";
var object = {
    name : "My Object",
    getNameFunc : function(){
        var that = this;   //而this指向object，所以that指向object。无论你执行多少次，他都是对object的引用，所以输出My Object
        return function(){
            return that.name;
        };
    }
};
alert(object.getNameFunc()());
```



