##Flex布局(弹性布局)
* 设置Flex布局之后，子元素的float、clear、vertical-align失效
* 容器属性：
    * flex-direction 主轴方向(4)
    * flex-wrap 一条轴排不下如何换行(3)
    * flex-flow 是flex-direction和flex-wrap的简写形式
    * justify-content 项目在主轴上的定义方式(5)
    * align-items 项目在交叉轴上如何对齐(5)
    * align-content 多根轴线的对齐方式(6)

* 项目属性：    
    * order:<integer> 数值越小排列越向前（默认0）    
    * flex-grow 定义项目的放大比例(默认为0)    

            1、如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。    
            2、如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。  
            

    * flex-shrink定义了项目的缩小比例(默认为1) 

            1、如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。
            2、如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小

    * flex-basic 定义了在分配多余空间之前，项目占据的主轴空间（main size)
    * flex 是flex-grow,flex-shrink,flex-basic的简写 默认值0 1 auto    

            1、该属性有两个快捷键auto(1 1 auto)和 none(0 0 auto)

    * align-self 

            1、允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。
            2、默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
