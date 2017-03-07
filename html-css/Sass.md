##Sass
<hr />
##编译风格
* nested        默认的嵌套缩进风格
* expanded      没有嵌套缩进风格
* compact       简洁格式的风格
* compressed    压缩后的css代码(一般生产环境使用)


```sass --style compressed test.css test.css```


##基本功能
* 监听文件或目录

        sass --watch input.css:output.css    
        sass --watch app/sass:public/stylesheets

* 变量       

        $bule: #1875e7;
        div {
            color: $blue;
        }


        $side: left;
        .round {
            border-#{$side}-radio: 10px;
        }


* 计算

        body {
            margin: (14px/2);
            top: 50px + 30px;
            right: $var * 10%;
        }

* 嵌套

        div {
            h1 {
            color: red;
            }
        }

* 注释
    * 除了标注的css注释还有sass特有的 `/*!*/`
    * 静默注释 `//`只会出现在sass文件中

##复用代码
* 继承
    
        .class {
            border: 1px solid #ddd;
        }

        .class2 {
            @extend .class1;
            font-size: 120%;
        }

* Mixin混合器
    
        @mixin left($value: 5px;) {
            float: left;
            margin-right: $value;
        }

        div {
            @include left(20px);
        }

* import插入文件
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
* 特殊结构`&`
    * 父选择器的标识符
    
* 默认变量值
    * !default 类似于！important的反值


##高级用法
* if else 语句
* for while each语句

##自行编写函数