# 字体
## 一、样式规则
### 1. 字体样式 font-
> color 字体颜色    

> font-style 字体样式  
        >* italic  斜体  
        >* normal  正常字体【默认】
    
>font-weight 字体粗细  
        >* normal  正常字体【默认】
        >* bold    粗体
        >* lighter 更细的字体
        >* 100~900 数字越大，字体越粗
    
>line-height 行高  
    取值等于该字体的包裹元素的高度  
    `line-height:200px;`  
    将文本文字在标签中垂直居中  
    ` <div style='height:200px;'> </div>`  
    
> font-size 字体大小  
         _浏览器默认字体大小为16px_
    
> font-family 字体族  
        > _可设置字体栈，防止电脑中缺少前面的字体_
        >* 字体族的名称  
        >> '微软雅黑'  
         'Miscrosoft YaHei'  
         serif 有衬线  
         sans-serif 无衬线  
         fangsong   政府文件      
>* font速写规则
    >>1. 必须包含font-size、font-family
    >>2. font-style、font-weight必须在font-size之前
    >>3. font-family必须在最后  
    font:font-style font-weight font-size font-family;
    
font设置示例：

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>字体样式</title>
    </head>
    <style>
        div {
        color: blue;
        /* font-style: italic;
        font-weight: lighter; */
        height:200px;
        background-color:#ccc;
        line-height: 200px;
        /* font-size: 17px;
        font-family: sans-serif,fangsong; */
        font:italic lighter 17px sans-serif,fangsong;
        }
    </style>
    <body>
        <div>hello world，你好世界</div>
        <h1>标题</h1>
    </body>
    </html>

### 2.文本样式 text-
> text-align 当前文本在元素中的对齐方式  
        >> left  
        center  文本水平居中
        right   
        justify 两端对齐 

> text-decoration 文本的线
        >> underline   下划线  
        overline    上划线  
        line-through 删除线  
        text-indent 首行缩进 2em    

> text-transform 文本变形，特指英文字符
        >>capitalize  首字母大写  
        uppercase   全部大写  
        lowercase   全部小写  

> text-shadow 文本的阴影
        >>px  x轴偏移量  
        px  y轴偏移量  
        blur 模糊程度  
        color 阴影颜色  
        text-shadow: 10px 5px 5px #333;与box-shadow取值相同

文本样式设置实例：

	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>文本样式</title>
	</head>
	<style>
	    div {
		width:200px;
		background-color:#ccc;
		text-align: center;
		text-decoration: overline;
		text-transform:lowercase;
		text-shadow: 5px 5px 2px #333;
		cursor: pointer;
	    }
	    a {
		text-decoration: none;
		color: black;
		cursor: wait;
	    }
	</style>
	<body>
	    <div>hello</div>
	    <a href="">12233344</a>
	</body>
	</html>

### 3.列表样式  

    list-style:none;  
    list-style-type;

### 4.单位
1. 颜色 color
    1. 关键字  
        red、black...  
        color:red;
    2. 十六进制颜色  
            #ededed  
            #333333 ==> #333  
            color:#333;  

    3. rgb函数  
        r red  
        g green  
        b blue  
        0 ~ 255  
        color:rgb(255,255,0);

    4. rgba函数  
        r red  
        g green  
        b blue  
        0 ~ 255  
        /*a 颜色透明度*/  
        0 ~ 1小数  
        color:rgba(0,0,0,0.5);  
    5. 渐变色
            background-image:  
            linear-gradient(to right,red,#ccc);  
            从左向右，从红色渐变到#ccc

2. 尺寸   
    绝对单位
        px 像素；rpx（小程序自适应）  
    相对单位
        em  
    > 1em=当前文本父元素的font-size  
        `<div style='font-size:12px;'></div>`  
            1em = 12px;
            2em = 24px;  
        % 相对于父元素   
            .left{  
                height:100%;  
            }

### 5.文本的水平垂直居中、子元素在父元素中水平垂直居中
> 文本  
    >* 水平：text-align:center;  
    >* 垂直：line-height:父元素的高度;
        
> 标签
    >> 父元素  
        display:table-cell;  
        vertical-align: middle;  
        align-items: center;  
    >> 子元素  
        display:inline-block;

 _如何消除a标签的默认样式？_  
* `text-decoration: none;`  
`color: black;`  
`cursor: default;`//提示;pointer 手 wait 等待
help 问号

_rgba和opacity的区别？_  
* rgba 会给父元素设置透明度，但是不会影响到子元素
    opacity 会给父元素设置透明度，会影响到子元素

## 二、网络字体 _webfont_ 
> @font-face  
> .ttf

1.下载ttf字体文件
2.将文件放到相对应的目录下
3.通过@font-face引入
    
    @font-face {  
        font-family: 'test';  
        src: url('./文件名.ttf');
    }

4.使用字体

    div {
        font-family:test;
    }

### 1.字体图标库
_iconfont、fontawesome_  使用\<i>\</i>
    
    webfont设置实例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>网络字体</title>
	</head>
	<style>
	    @font-face {
		font-family: 'myfont';
		src: url('./HYSIJIATiW.ttf');
	    }
	    div {
		font-family: myfont;
	    }
	</style>
	<body>
	    <div>hello world，你好世界</div>
	</body>
	</html>
