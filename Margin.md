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

>存在传递问题，子级会把自己的`margin-top `和`margin-bottom`传递给父级 ，只会左右传递不会上下传递。


>解决办法：方法之一给父级添加一个`border`   

