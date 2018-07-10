1.标签语义化以及使用好处

平时用的语义标签

H1-H6 标题内容

p 段落

ul 无序

ol 有序

dl 定义列表   &lt;dt&gt;标题&lt;/dt&gt;   &lt;dd&gt;内容&lt;/dd&gt;

thead 表格中的表头内容

tbody 表格中的主体内容

h5中的语义标签

header

footer

aside

section

nav

progress   &lt;progress value="22" max="100"&gt;  
&lt;/progress&gt;

video

好处：

[http://www.css88.com/archives/166](http://www.css88.com/archives/1668)

[https://www.cnblogs.com/nanshanlaoyao/p/6402721.html](https://www.cnblogs.com/nanshanlaoyao/p/6402721.html)   \(SEO优化\)

1. **去掉或样式丢失的时候能让页面呈现清晰的结构**
2. 浏览器的默认样式和语义化的HTML结构是不可分割的
3. html语义化让页面的内容结构化，结构更清晰，便于对浏览器，搜索引擎解析
4. 搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
5. **便于团队开发和维护**

   **因为爬虫很大程度上会忽略用于表现的标记,而只注重语义标记.**

   SEO（Search Engine Optimization）翻译为搜索引擎优化。seo是专门利用搜索引擎的搜索规则来提高目前网站在有关搜索引擎内的自然排名的方式。

2. http 加载过程

浏览器渲染页过程描述

1. 浏览器解析html源码，然后创建一个DOM树。

2. 浏览器解析CSS代码，计算出最终的样式数据。

3. 创建完DOM树并得到最终的样式数据之后，构建一个渲染树。

4. 当渲染树创建完成之后，浏览器就可以根据渲染树直接把页面绘制到屏幕上。



