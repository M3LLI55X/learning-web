# 盒子模型
    文档中的每个元素都可以被看作是一个矩形盒子
## 1. 盒子属性
    > width  
    > height  
    > margin 外边距  
       >> 盒子与其他盒子之间的距离  
       >> margin-top 上外边距  
        margin-right 右外边距  
        margin-bottom 下外边距  
        margin-left 左外边距  

        margin:10px;    上下左右都为10px
        margin:5px 10px; 上下为5px，左右为10px  
        margin:5px 10px 15px; 上为5px，左右为10px，下为15px  
        margin:5px 10px 15px 20px; 上5px，右10px，下15px，左20px

    > border 边框  
        border-width    边框线宽  
            px  
        border-style    边框样式:
                ```solid   实线  
                dotted  点状线  
                dashed  虚线  
                double  双实线```  
        border-color    边框颜色  
        
        速写：
            border:1px solid #ccc;

    > padding 内边距:
        盒子边框与内容之间的距离    
    background-color    背景颜色  
    background-image    背景图片  
    background-repeat   背景图片重复的方式:
        ```no-repeat
        repeat-x
        repeat-y```  
    background-size     背景图片尺寸  
        background-size: 100% 100%;
        阴影：`box-shadow:10px 5px 5px #333;`

## 2. 盒子组成  
    width、padding(内边距)、border、margin

## 3. 盒子分类 
    _通过box-sizing可以设置盒子的类型_
    1. box-sizing:content-box;【内容盒子】【W3C标准盒子】
        width = 内容width
        所占的宽 = width + border + padding + margin

    2. box-sizing:border-box;【边框盒子】【IE盒子】小很多
        width = 内容width + border + padding

    盒子模型示例：
    ```1.
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>盒子模型</title>
    </head>
    <style>
        div {
        width:200px;
        height: 200px;
        background-color: #ccc;
        /* border-width:10px;
        border-style: solid;
        border-color: #333; */
        border: 10px solid #333;
        background-image: url('./2.png');
        /* background-repeat: repeat-x; */
        background-size: 100% 100%;
        } 
    </style>
    <body>
        <div></div>
    </body>
    </html>
    ```
    ```
    2.
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <style>
        .one {
        height: 200px;
        width:200px;
        background-color: red;
        border:10px solid #ccc;
        padding:10px;
        box-sizing: content-box;
        }
        .two {
        height: 200px;
        width:200px;
        background-color: #333;
        border:10px solid #ccc;
        padding:10px;
        box-sizing: border-box;
        }
    </style>
    <body>
        <div class="one"></div>
        <div class="two"></div>
    </body>
    </html>
    ```

## 4. 边框塌陷（margin塌陷）  
   浏览器中上下排布的两个盒子之间的距离，取其中margin较大的那个值，不会相加
   水平方向则不会出现此现象

## 5. 定位布局 _position_  
_用法：当一个元素悬挂在另一个元素之上时，一般采用定位布局_	    

* 案例：模态框、二级下拉菜单

* 特点：  
    * 元素可能会脱离文档流   
    * 可以使用left、right、top、bottom来描述元素的位置

* 取值：
	> static  静态布局 

    > relative  相对定位
        >1. 不脱离文档流  
        >2. 参考点：相对于当前元素的原本位置
    >>* _网页中有两个嵌套关系的盒子，外层盒子和内层盒子之间有一定距离，如何设置？_  
        >>1. 将子元素设置为相对定位  
                `position:relative;`   
                `top:50px;`
        >>2. 给父元素设置上内边距  
                `padding-top:50px;`  
                `box-sizing:boder-box;`  
        >>3. 子元素设置浮动  
                `float:left;`  
                `margin-top:50px;`
        >>4. 子元素设置绝对定位，父元素设置相对定位  
                子元素： 
                `position:absolute;`
                `top:50px;`
                父元素：  
                `position:relative;`
    >>* _子元素在父元素中水平垂直居中？_  
       >>1. 将父元素设置相对定位，子元素设置为绝对定位  
            子元素： 
            `top:0;`   
            `left:0;`
            `right:0;`
            `bottom:0;`
            `margin:auto;`
       >>2. 将父元素设置相对定位，子元素设置为绝对定位   
            `left:50%;`  
            `top:50%;`
            `margin-left:-当前元素宽度的一半;`
            `margin-top:-当前元素高度的一半;`
            `box-sizing:boder-box;`  
       >>3. 设置display:table-cell;
       

    > absolute  绝对定位
        >1) 脱离文档流
        >2) 参考点：相对于当前元素的父定位元素，如果父元素中没有定位元素，则相对于浏览器视口

    > fixed   固定定位
        >1) 脱离文档流
        >2) 参考点：相对于浏览器视口

    > sticky  粘滞定位
        >1) 不脱离文档流
        >2) relative与fixed的结合  
            position:sticky;  
            top:100px;  
            当当前元素距离浏览器视口上方100px时，体现固定定位的特点

    > display
        >* flex：将盒子设置为伸缩盒
        >* flex-direction  主轴的方向  
            column  行布局 ，子元素会在y轴方向上排布  
            row   列布局【默认】，子元素会在x轴方向上排布
        >* flex-wrap   设置换行    
            当所有子元素的宽/高超出父元素的宽/高的时候，设置换行  
            wrap    超出时换行  
            nowrap  超出时不换行【默认】
        >* flex 速写
            flex-grow	flex容器中剩余空间的多少应该分配给项目  
            flex-shrink	指定了flex 元素的收缩规则  
            flex-basis	指定了flex 元素在主轴方向上的初始大小
        >* align-items 
            center  在交叉轴上居中显示
        >* justify-content
            center 在主轴上居中显示
            justify-content: flex-start; /* 从行首起始位置开始排列 */
            justify-content: flex-end;   /* 从行尾位置开始排列 */
    
    > 注意：
    >1. 父元素需要在主轴方向上有固定宽/高，供子元素分配
        flex-basis
    >2. 子元素的默认宽/高会在交叉轴上占满父元素
        主轴为x轴时，子元素默认高度会占满父元素
        主轴为y轴时，子元素默认宽度会占满父元素

## 6. 如何使元素在网页中自适应水平居中
    
    margin: 0 auto; 
    使用前提：将元素设置为块级元素
    
> 块级元素  
    >1. 设置高度
    >2. 设置`margin: 0 auto; `
> 行内元素
    >0. 设置为块元素 
    >1. 设置宽度之前，需要将行内元素设置为块级元素或者是行内块级元素  
    >2. 设置`margin: 0 auto;`
> 行内块元素  _input_
    >1. 设置为块级元素 
    >2. 设置`margin: 0 auto; 
   
## 拓展：
### 1.overflow的取值
> 使用前提：当前元素需要有给定的高度和宽度
>> hidden 将超出的内容隐藏，不会出现滚动条  
    auto 自适应的加上滚动条，如果内容没有超出，则没有滚动条，如果内容超出，则加上滚动条  
    scroll 始终加上滚动条，不管内容有没有超出    

    overflow-x:scroll/aoto/hidden; x轴方向滚动条
    overflow-y:scroll/auto/hidden;
    overflow:scroll/auto/hidden;

## 伸缩盒布局 
1. 作用:响应式布局（手机端开发）
2. 用法与浮动类似，都是将子元素在父元素中排列
3. 属性：
     * display:flex;将盒子设置为伸缩盒
     * flex-direction:主轴的方向：  
        column  行布局
         row 列布局（默认值）子元素会在x轴方向上排布 
     * flex-wrap 设置换行：当所有子元素的宽/高超出父元素的宽/高的时候，设置换行  
        wrap 超出时换行
        nowrap 超出时不换行
    * flex 速写
        flex-basis：指定了flex元素在主轴方向上的初始大小  
        flex-grow flex容器中剩余空间的多少应该分配给项目（flex增长系数）  
        flex-shrink 指定了flex元素的收缩规则  
_*浮动布局与绝对定位脱离文档流_
