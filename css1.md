# 什么是css
## 层叠样式表,用于修饰页面元素

层叠：多个元素用于修饰一个页面元素
    
    样式表（声明块）
        {
            color:'red';
        }
# css3语法
    选择器 {
        样式名：样式值
    } 
    /*eslint报警告*/
# 可读性
## 空白(缩进)
    div{
        color:'red';
        font-size:'19px'
    }
## 注释
    /*注释*/
## 速记写法
    padding:5px 10px 15px 20px; //上右下左
    等价于
    padding-top:5px;
    padding-right:10px;
    padding-bottom:15px;
    padding-left:20px;
## 选择器组
    .one , .three{
        color:'red';
    } 
    <div class='one'>1</div>
    <div>2</div>
    <div class='three'>3</div>
## css样式如何用于html
### 外部link导入——外部样式表,从head引入
    <link rel="stylesheet" href="">
### 内部style标签——内部样式表
    <style>
    
    </style>
### 标签内部style属性——内联样式表
    ！ 优先级最高
    <div style='样式名：样式值；样式名：样式值；'></div>
### @import导入
    <style>
        @import './路径';
    </style>
## Link和@import的区别
1. 所属范围  
    * link是个标签，不仅仅可以导入样式表，还可以设置rel属性
        rel="stylesheet"代表导入外部样式表  
    * @import是css的语法，只能导入样式表
2. 加载顺序  
    Link标签导入的样式是在浏览器加载标签的同时加载的  
    @import导入的样式是在文档加载完毕之后再加载的

    文档加载完毕之后的方式  
        `window.onload=function(){}`  
        `$(function(){})`
3. 兼容性  
    link是一个html标签，没有兼容性问题
    @import有兼容性问题
## css工作原理
1. 浏览器加载html文件
2. 浏览器解析html文件  
        如果存在css文件，就加载css文件，然后解析css文件
3. 将解析后的文件创建成dom树，进行显示 
