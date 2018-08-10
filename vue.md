搭建环境：[https://www.cnblogs.com/RexSheng/articles/6934413.html](https://www.cnblogs.com/RexSheng/articles/6934413.html)

vue方法：

methods：定义方法

computed：计算属性

生命周期

created: 数据的初始化，异步请求也适宜在这里调用。

mounted: 通常是初始化页面完成后，再对html的dom节点进行一些需要的操作

```
beforeCreate:function(){
    console.log('beforeCreate:刚刚new Vue()之后，这个时候，数据还没有挂载呢，只是一个空壳')           
    console.log(this.msg)//undefined
    console.log(document.getElementsByClassName("myp")[0])//undefined
},
created:function(){
    console.log('created:这个时候已经可以使用到数据，也可以更改数据,在这里更改数据不会触发updated函数')
    this.msg+='!!!'
    console.log('在这里可以在渲染前倒数第二次更改数据的机会，不会触发其他的钩子函数，一般可以在这里做初始数据的获取')
    console.log('接下来开始找实例或者组件对应的模板，编译模板为虚拟dom放入到render函数中准备渲染')
},
beforeMount:function(){
    console.log('beforeMount：虚拟dom已经创建完成，马上就要渲染,在这里也可以更改数据，不会触发updated')
    this.msg+='@@@@'
    console.log('在这里可以在渲染前最后一次更改数据的机会，不会触发其他的钩子函数，一般可以在这里做初始数据的获取')
    console.log(document.getElementsByClassName("myp")[0])//undefined
    console.log('接下来开始render，渲染出真实dom')
},
// render:function(createElement){
//     console.log('render')
//     return createElement('div','hahaha')
// },
mounted:function(){ 
    console.log('mounted：此时，组件已经出现在页面中，数据、真实dom都已经处理好了,事件都已经挂载好了')
    console.log(document.getElementsByClassName("myp")[0])
    console.log('可以在这里操作真实dom等事情...')

//    this.$options.timer = setInterval(function () {
//        console.log('setInterval')
//         this.msg+='!'  
//    }.bind(this),500)
},
beforeUpdate:function(){
    //这里不能更改数据，否则会陷入死循环
    console.log('beforeUpdate:重新渲染之前触发')
    console.log('然后vue的虚拟dom机制会重新构建虚拟dom与上一次的虚拟dom树利用diff算法进行对比之后重新渲染')         
},
updated:function(){
    //这里不能更改数据，否则会陷入死循环
    console.log('updated:数据已经更改完成，dom也重新render完成')
},
beforeDestroy:function(){
    console.log('beforeDestory:销毁前执行（$destroy方法被调用的时候就会执行）,一般在这里善后:清除计时器、清除非指令绑定的事件等等...')
    // clearInterval(this.$options.timer)
},
destroyed:function(){
    console.log('destroyed:组件的数据绑定、监听...都去掉了,只剩下dom空壳，这里也可以善后')
}
```

webstrom环境配置

1.语言改成es6

2.File Types中添加    \*.vue

3.在plugins中搜索   vue，安装

4.在文件中解决报错

（1）在script标签上添加属性  type="es6"

（2）Settings &gt;Language Injections添加![](/assets/1055753-20170605164939622-835671294.png)

**1.npm是什么？**

• 允许用户从NPM服务器下载别人编写的第三方包到本地使用。

• 允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用。

• 允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用。

**2.为什么安装镜像？**

由于有些npm有些资源被屏蔽或者是国外资源的原因，经常会导致用npm安装依赖包的时候失败

**3.什么是vue-cli**

vue-cli 是vue.[js](http://lib.csdn.net/base/javascript)的脚手架，用于自动生成vue.js+webpack的项目模板

**4.webpack**

webpack是构建工具、模块打包器，也就是整个项目是基于webpack的

node\_modules：项目依赖包资源

运行命令 npm run dev ，会用热加载的方式运行我们的应用，热加载可以让我们在修改完代码后不用手动刷新浏览器就能实时看到修改后的效果

vue-router用来做前端路由，可以方便你实现vue组件之间显示的切换、参数传递之类

![](/assets/10868449-01a038fa573b22c8.png)

watch：[https://blog.csdn.net/wandoumm/article/details/80259908](https://blog.csdn.net/wandoumm/article/details/80259908)

[https://www.jianshu.com/p/514c7588e877](https://www.jianshu.com/p/514c7588e877)

[https://www.xiuyuan.info/?p=230](https://www.xiuyuan.info/?p=230)

[https://www.jianshu.com/p/ec436222c608](https://www.jianshu.com/p/ec436222c608)

vue-infinite-loading2.0 中文文档

[https://www.jianshu.com/p/bfb5ca56b4fb](https://www.jianshu.com/p/bfb5ca56b4fb)

解释webpack文件

[https://segmentfault.com/a/1190000008644830](https://segmentfault.com/a/1190000008644830)

重定向：指向的是redirect的路径

别名：指向的是path的路径（alias）

