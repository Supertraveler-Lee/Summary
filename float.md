#float浮动
<hr />

##目录
* [相关概念](#相关概念)
* [为什么会出现浮动](为什么会出现浮动)
* [触发hasLayout的条件](#触发hasLayout的条件)
* [如何触发BFC](#如何触发BFC)
* [BFC特性](#BFC特性)
* [常用闭合浮动解决方法](#常用闭合浮动解决方法)    
    * [使用带clear的空标签或者br标签](#使用带clear的空标签或者br标签)    
    * [使用::after伪元素](#使用after伪元素)
    * [使用`overflow`属性`hidden`或者`auto`](#使用overflow属性hidden或者auto)
    * [将容器设置成`float`](#将容器设置成float)
    * [父元素设置`display:table`](#父元素设置display:table)
* [总结](#总结)

##<a id="相关概念">相关概念</a>：

* BFC (block formatting contexts  )
> 块级元素格式化上下文  CSS3称之为 `flow root`
* 文档流   
>文档流是文档中可显示对象在排列时所占用的位置 
* 闭合浮动   
>避免float无法撑高父容器的默认行为
* 清除浮动   
>使用clear阻止这个元素盒子的边和前面的浮动元素相邻的行为

##<a id="为什么会出现浮动">为什么会出现浮动</a>
```浮动出现的意义其实只是用来让文字环绕图片而已，仅此而已 。```

##<a id="触发hasLayout的条件">触发hasLayout的条件</a>
* `position` : absolute
* `float` : left|right
* `displa`: inline-block
* `width` : 除 “auto” 外的任意值
* `height` : 除 “auto” 外的任意值 
* `zoom` : 除 “normal” 外的任意值 
* `writing-mode` : tb-rl

##<a id="如何触发BFC">如何触发BFC</a>
* float 除了none以外的值
* overflow除了visible以外的值（hidden，auto，scroll ）
* display (table-cell，table-caption，inline-block)
* position（absolute，fixed）
* fieldset元素

##<a id="BFC特性">BFC特性</a>
1、块级格式化上下文会阻止外边距叠加
>如果这两个相邻的块框不属于同一个块级格式化上下文，那么它们的外边距就不会叠加。     

2、块级格式化上下文不会重叠浮动元素
>一个块级格式化上下文的边框不能和它里面的元素的外边距重叠。即浏览器将会给块级格式化上下文创建隐式的外边距来阻止它和浮动元素的外边距叠加 。

3、块级格式化上下文通常可以包含浮动

 
##<a id="常用闭合浮动解决方法">常用闭合浮动解决方法</a>
"
* 在float同级最后方加入带有clear:both属性的元素或伪元素    
* 给父级加上一些overflow/float/display table等触发BFC的属性以使父容器成为block formatting context     

<hr />

1、<a id="使用带clear的空标签或者br标签">使用带clear的空标签或者br标签</a>
>太多空标签，不符合样式行为相分离的原则。
```html
    <style type="text/css">
        .clean {clear:both;}
    </style>

    <div class="containter">
        <div class="floatleft">向左浮动</div>
        <div class="floatright">向右浮动</div>
        <div class="clean">空标签</div>  
    </div>
     
```

2、<a id="使用after伪元素">使用::after伪元素</a>
>after默认行内元素，这个用法的after只针对块元素。推荐用法

```html
    <style type="text/css">
        .clearfix::after {
            dislpay:block;
            clear:both;
            content:'';
        }
        /*IE6、IE7不支持伪元素，需要触发haslayout或者写入CSS hacker文件里*/
        .clearfix {
            *zoom:1;
        }
    </style>

    <div class="containter">
        <div class="floatleft"></div>
        <div class="floatright"></div>
    </div>

```

3、<a id="使用overflow属性hidden或者auto">使用`overflow`属性`hidden`或者`auto`</a>
>浮动导致脱离文档流，而`overflow`可以使文档重回文档流，把容器高度撑起。
>内容增多时候容易造成不会自动换行导致内容被隐藏掉，无法显示需要溢出的元素。
>甚至会导致中键不能用。

```html
    <style type="text/css">
        .container{
            overflow:hidden;
        }
    </style>
        
    <div class="containter">
        <div class="floatleft"></div>
        <div class="floatright"></div>
    </div>
```

4、<a id="将容器设置成float">将容器设置成`float`</a>
>同overflow法一样无须添加额外的class，使用方便但是会对下面的文档造成影响。

```html
    <style type="text/css">
        .menu{
            clear:left;
        }
    </style>
    <ul class="menu">
        <li class="floatleft">
        <li class="floatright">
    </ul>
```
5、<a id="父元素设置display:table">父元素设置`display:table`</a>
>还是存在兼容问题，`display:table`系列样式设定不在IE6/7的支持范围之内。


```html
    <style type="text/css">
        .container{
            display: table;
        }
    </style>
        
    <div class="containter">
        <div class="floatleft"></div>
        <div class="floatright"></div>
    </div>
```

##<a id="总结" >总结</a>
**所以在支持BFC的浏览器（IE8+，firefox，chrome，safari）通过创建新的BFC闭合浮动；
在不支持 BFC的浏览器 （IE6-7），通过触发 hasLayout 闭合浮动。**
<hr />

<strong>注</strong>：  

    1、当一个元素浮动之后，不会影响到块级框的布局而只会影响内联框（通常是文本）的排列。
    2、非浮动元素里的内容会留出前面浮动元素的位置(盒模型的位置)，可能和属于同一box有关（inline-box）。
    3、inline-box与line-box的概念、float与inline-block的区别

