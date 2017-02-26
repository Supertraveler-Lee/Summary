
##Sass
<hr />
##编译风格
* nested        默认的嵌套缩进风格
* expanded      没有嵌套缩进风格
* compact       简洁格式的风格
* compressed    压缩后的css代码(一般生产环境使用)    

```css
sass --style compressed test.css test.css```   

##监听文件或目录
```css
sass --watch input.css:output.css
sass --watch app/sass:public/stylesheets

##基本功能
* 变量
    ```sass
    $bule: #1875e7;
    div {
        color: $blue;
    }```

    ```sass
    $side: left;
    .round {
        border-#{$side}-radio: 10px;
    }```

* 计算
    ```sass
    body {
        margin: (14px/2);
        top: 50px + 30px;
        right: $var * 10%;
    }```

* 嵌套
    ```sass
    div {
        h1 {
        color: red;
        }
    }

* 注释
    * 除了标注的css注释还有sass特有的 `/*!*/`
