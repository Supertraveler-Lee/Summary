##定位
<hr />
##目录
* [浮动常用值](#浮动常用值)
* [absolute特性](#absolute特性)
* [relative特性](#relative特性)
* [z-index特性](#z-index特性)

![](https://leohxj.gitbooks.io/front-end-database/content/html-and-css-basic/assets/Visual-formatting-model.jpg)
###<a id="浮动常用值">浮动常用值</a>
* static
* relative
* absolute
* fixed
* center、page、sticky(CSS3)

##<a id="absolute特性">absolute特性</a>
* 包裹性和破坏性       
    * 包裹性导致把元素inline-block化，导致块级元素宽度变成由内容撑开。    
    * 完全脱离文档流显示了其破坏力。
* 元素原来的位置会被其他元素替代
* 常用来实现等高布局
* 控制元素显隐     
```css
常见控制显隐方法

.hidden {
    position: absolute;
    top: -9999em;
}
.hidden {
    position: ansolute;
    visilibity: hidden; /*对辅助类设备不友好*/
}
.hidden {
    position: absolute;
    clip: rect(1px 1px 1px 1px) /* IE6 7*/
    clip: rect(1px, 1px, 1px, 1px)
}
```


##<a id="relative特性">relative特性</a>
* 元素的位置不会被其他元素替代
* 相对定位的最小化原则

##<a id="z-index特性">z-index特性</a>
* 只有在position属性非static的情况下使用
