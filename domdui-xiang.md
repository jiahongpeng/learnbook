原生查找元素的方法

1.document.getElementById\('id'\);  //返回元素对象

获取元素中的内容   innerHTML

速度比较慢

2.getElementByTagName\('标签'\)   //返回的是类数组对象

node.setAttribute\('属性名'，‘属性值’\)；

3.document.getElementByName\('name属性的值'\)   //返回的是类数组对象

4.document.getElementByClassName\('class'\)   //\(IE9以后\)  类数组对象

5.element.querySelector\('\#c'\)   //或者   .c   //返回一个对象

element.querySelectorAll\('.class'\)    //返回一个类对象

var x = document.getElementById\("myDIV"\);

x.querySelector\("\#demo"\).innerHTML = "Hello World!";

href=‘’；刷新当前页面

href=‘\#’    跳转到当前页面的起始点

