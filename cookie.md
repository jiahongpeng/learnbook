```
<script language="JavaScript" type="text/javascript"> 
<!-- 
//设置两个cookie 
document.cookie="userId=828"; 
document.cookie="userName=hulk"; 
//获取cookie字符串 
var strCookie=document.cookie; 
//将多cookie切割为多个名/值对 
var arrCookie=strCookie.split("; "); 
var userId; 
//遍历cookie数组，处理每个cookie对 
for(var i=0;i<arrCookie.length;i++){ 
var arr=arrCookie[i].split("="); 
//找到名称为userId的cookie，并返回它的值 
if("userId"==arr[0]){ 
userId=arr[1]; 
break; 
} 
} 
alert(userId); 
//--> 
</script>
```



