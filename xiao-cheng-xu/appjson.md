```
//设置标题栏
{
  "pages": [
    "pages/index/index",
    "pages/detail/detail"
  ],
  "window": {
    "backgroundTextStyle": "light",
    "navigationBarBackgroundColor": "#42BD56",
    "navigationBarTitleText": "豆瓣图书",
    "navigationBarTextStyle": "white"
  },
  "tabBar":{
    "backgroundColor":"#fff",
    "color":"#666",
    "borderStyle":"black",
    "selectedColor":"#666",
    "position":"bottom",
    "list":[{
      "pagePath": "pages/index/index",
      "text":"首页",
      "iconPath":"images/book.png",
      "selectedIconPath":"images/book.png"
    },{
      "pagePath": "pages/detail/detail",
      "text": "详情",
      "iconPath": "images/book.png",
      "selectedIconPath": "images/book.png"
    }]
  }
}
```



