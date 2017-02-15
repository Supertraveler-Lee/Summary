##定位
<hr />
##目录
* [浮动常用值](#浮动常用值)
* [absolute特性](#absolute特性)
* [relative特性](#relative特性)
* [常见`position:absolute`布局替代方案](#常见`position:absolute`布局替代方案)

###<a id="浮动常用值">浮动常用值</a>
* static
* relative
* absolute
* fixed
* center、page、sticky(CSS3)

##<a id="absolute特性">absolute特性</a>
>1、包裹性和破坏性
    1、包裹性导致把元素inline-block化，导致块级元素宽度变成由内容撑开。
    2、完全脱离文档流显示了其破坏力。
2、元素原来的位置会被其他元素替代


##<a id="relative特性">relative特性</a>
>1、元素的位置不会被其他元素替代


##<a id="常见position:absolute布局替代方案">常见`position:absolute`布局替代方案</a>
* margin-top代替relative + absolute + top
* 单独使用absolute而不利用top等属性
