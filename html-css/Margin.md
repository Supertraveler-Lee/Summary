##margin
* margin常用来做什么
    * 让块元素水平居中；
    * 让元素之间留有舒适的留白；
    * 处理特殊的first或last，大家懂的？
    * 一些布局；

* margin 需要注意的地方
    * margin折叠；
    * margin的百分比值；
    * margin的auto值；
    * margin和相对偏移top, right, bottom, left的异同；
    * IE6浮动双margin Bug；
    * IE6浮动相邻元素3px Bug；

####1、`margin:auto`等同于`margin: 0 auto`？     

    前提是书写模式和文档流是默认的，即writing-mode: horizontal-tb; direction: ltr;
####2、margin百分比
```css
    <style type="text/css">
        .demo{
            height: 100px;
            width: 60px;
        }
        .demo p{
            margin: 10% 5%;
        }
    </style>
    <div class="demo">
        <p>something</p>
    </div>
    /*由于文档流和书写模式的原因，最终margin的top、left值是50px和25px而不是50px和30px。*/
```

####3、margin与相对偏移top、bottom等的区别
    
    margin主要是用来增加自身与其他元素的空白(互动)
    top、bottom是对自身进行排版(孤独)

>   position为relative时，如果top和bottom都是auto，则它们的计算值是0     
    如果top和bottom其中一个为auto，则auto相当于另一个的负值。     
    如果top和bottom的值都不为auto，则忽略bottom。     
    如果right和left的值都不为auto，则忽略right。

      
####4、发生折叠需要是相邻的非浮动元素     
####5、受书写模式的影响的因素     

    margin折叠
    margin的keyword auto value
    padding的百分比值

####6、如何避免margin折叠     

    margin 折叠元素只发生在块元素上
    浮动元素不与其他元素 margin 折叠
    定义了属性overflow且值不为visible（即创建了新的块级格式化上下文）的块元素，不与它的子元素发生margin 折叠
    绝对定位元素的 margin 不与任何 margin 发生折叠
    特殊：根元素的 margin 不与其它任何 margin 发生折叠


####7、margin实现等高布局
```css
    <style type="text/css">
        #doc{
            overflow: hidden;
        }
        #main,#aside{
            margin-bottom: -999px;
            padding-bottom: 999px;
        }
    </style>
    <div id="doc">
        <div id="main">主要内容<br />占位内容</div>
        <div id="aside">侧边栏</div>
    </div>
```
  
####8、margin浏览器bug      

    IE6浮动双倍margin 
    产生条件：
    block + 浮动 + margin 
    解决办法：
    1、 _margin-left 单独hack
    2、_dislpay: inline  更优

    IE8按钮margin auto居中失效Bug
    解决方案：
    不改变其display值，包含块text-align:center

    IE6浮动相邻元素3px
    IE6/7 clear引发的margin-top
    解决方案：
    设置了clear为非none值的元素，其顶部border边界在垂直方向不允许出现在之前的浮动元素底部margin之上


####9.margin辅助布局

经典左右布局
```css
    <style type="text/css">/*absolute + margin*/
        #aside{
            position:absolute;
            top:0;
            right:0;
            width:200px;
        }
        #main{
            margin-right:210px;
        }
    </style>
    <header id="hd">header</header>
        <div id="bd">
            <div id="main">main</div>
            <aside id="aside">aside</aside>
        </div>
    <footer id="ft">footer</footer>
    /*致命缺点是absolute无法撑开容器*/
```
float+margin不支持优先显示
```css
    <style type="text/css">/*圣杯布局*/
        #bd{
            padding-left:210px;
        }
        #aside{
            float:left;
            position:relative;
            left:-210px;
            width:200px;
            margin-left:-100%;
        }
        #main{
            float:left;
            width:100%;
        }
    </style>
    <header id="hd">header</header>
        <div id="bd">
            <div id="main">main</div>
            <aside id="aside">aside</aside>
        </div>
    <footer id="ft">footer</footer>
```

注意点：    

    img是个行内置换元素，所以可以设置margin和宽高。
    置换元素拥有内在的二维属，宽高不完全由CSS决定，还受其自身内容和外部资源所影响
    常见的置换元素有哪些？
    img, object, button, input, textarea, select等

    存在传递问题，子级会把自己的`margin-top `和`margin-bottom`传递给父级 ，只会左右传递不会上下传递。     
    解决办法：方法之一给父级添加一个`border`   