# css选择器
## 一、基本选择器
### 1.标签选择器
> 含义：根据给定的标签名选取当前文件中所有具有该标签名的元素，设置属性

    语法：   
    标签名 {
        样式名:样式值;
    }

> 注意：
    > 1. 标签选择器可以选中当前文件中所有具有该标签名的元素，而不是某一个
    > 2. 不管具有该标签名的元素嵌套多少层，都可以被选中
    > 3. 只要是html的标签，都可以被用作于标签选择器

    标签选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>标签选择器</title>
	</head>
	<style    >
	    p {
		color: blue;
	    }
	</style>
	<body>
	    <p>段落一</p>
	    <p>段落二</p>
	    <ul>
		<li>
		    <ul>
			<li><p>段落三</p></li>
		    </ul>
		</li>
	    </ul>
	</body>
	</html>

### 2.类名选择器
> 含义：根据给定类名选取当前文件中所有具有该类名的元素，设置属性

> 语法：
    .类名 {
        样式名:样式值;
    }

> 注意：
    >1. 类名选择器的类名在同一文件中允许重复
    >2. 类名选择器的命名是有规范的
        数字、字母、下划线
        不能以数字开头
        不能以其他标签名作为类名
        .div .p .html...
    >3. 同一个元素可以有多个类名
        错误：<div class='类名一' class='类名二'></div>
        正确：<div class='类名一 类名二 ...'></div>
    >4. 类名选择器在使用的时候，需要在类名前加上.

    类名选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>类名选择器</title>
	</head>
	<style>
	    .person_two {
		color: teal;
	    }
	    .time {
		color: blue;
	    }
	    .person_one {
		color: red;
	    }
	</style>
	<body>
	    <p class='person_one time'>迟到</p>
	    <p class='person_two'>早退</p>
	</body>
	</html>
### 3.id选择器
> 含义：根据给定id取当前文件中具有该id的元素，设置属性

> 语法：
    #id {
        样式名:样式值;
    }

>注意：
    >1. 在同一个文件中，id的取值是唯一的
    >2. 同一个元素只能有一个id
    >3. 在使用id选择器时，需要在id前面加上#，不能有空格
        错误: # id {}
        正确: #id {}
    >4. id选择器的命名规范与类名选择器一致  

    id选择器实例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>id选择器</title>
	</head>
	<style>
	    #person_one {
		color: red;
	    }
	</style>
	<body>
	    <p id='person_one'>迟到</p>
	    <p id='person_two'>早退</p>
	    <p id='person_three'>按时</p>
	    <p id='person_four'>必成</p>
	</body>
	</html>

### 通配选择器
> 含义：选中当前文件中所有的标签，设置属性

> 语法：
    * {
        样式名:样式值;
    }

> 注意：
    用于初始化页面元素的样式

    通配选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>通配选择器</title>
	</head>
	<style>
	    * {
		list-style: none;
		margin: 0;
		padding: 0;
	    }
	    
	</style>
	<body>
	    <ul>
		<li>1</li>
		<li>2</li>
		<li>3</li>
		<li>4</li>
	    </ul>
	    <p>段落标签</p>
	</body>
	</html>
### 逗号选择器
>含义：给多个选择器同时选中的元素，设置属性

>语法：
    选择器一, 选择器二, ...{
        样式名:样式值;
    }

>注意：
    如果同一文件中有多个元素都需要设置同样的样式的时候，就可以使用逗号选择器

	逗号选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>逗号选择器</title>
	</head>
	<style>
	    .para_one,.para_three {
		color:teal;
		font-size: 40px;
		background-color: #ccc;
	    }
	    /* div.test {
		color: red;
	    } */
	</style>
	<body>
	    <!-- <div class='test'>这是一个div一</div>
	    <div>这是一个div二</div> -->
	    <p class='para_one'>段落一</p>
	    <p>段落二</p>
	    <p class='para_three'>段落三</p>
	</body>
	</html>
## 二、层次选择器
### 1.子代选择器
> 含义:先选中具有标签名一的元素，再在该元素的第一代子元素在选中具有标签名二的元素

>语法：
    标签名一 > 标签名二 {
        样式名:样式值;
    }

>注意：
    >1. 子代选择器只能选中第一代的子元素，如果出现嵌套关系，无法选中
    >2. 在使用子代选择器的时候，要使用 > 连接
    >3. 标签名的取值不仅仅可以是标签名，还可以是类名、id
   
    子代选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>子代选择器</title>
	</head>
	<style>
	    /* 子代选择器 */
	    /* .wrapper > p {
		color: blue;
	    } */

	    /* 后代选择器 */
	    .wrapper .one {
		color: blue;
	    }
	</style>
	<body>
	    <div class='wrapper'>
		<p class='one'>段落一</p>
		<p class='one'>段落二</p>
		<div>
		    <p class='one'>段落三</p>
		    <ul>
			<li><p class='one'>段落四</p></li>
		    </ul>
		</div>
	    </div>
	</body>
	</html>
### 2.后代选择器
> 含义:先选中具有标签名一的元素，再在该元素的所有子元素在选中具有标签名二的元素

> 语法：
    标签名一 标签名二 {
        样式名:样式值;
    }

> 注意：
    >1. 在使用后代选择器的时候，使用空格连接两个标签名
    >2. 子元素不论被嵌套多少层，都可以被选中
    >3. 标签名的取值不仅仅可以是标签名，还可以是类名、id

### 3.兄弟选择器
#### 相邻兄弟选择器
> 含义：给指定选择器后面紧跟的那个选择器选中的标签设置属性

> 语法：
        选择器一 + 选择器二 {
            样式名:样式值;
        }

> 注意：选中指定选择器后面紧跟的那个选择器选中的标签，两个标签中间不能有其他元素
#### 通用兄弟选择器
>   含义：给指定选择器后面的选择器选中的所有标签设置属性

>   语法：
        选择器一 ~ 选择器二 {
            样式名:样式值;
        }
        
	兄弟选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>兄弟选择器</title>
	</head>
	<style>
	    /* 相邻兄弟选择器 */
	    /* .para_one + p {
		color: blue;
	    } */
	    /* 通用兄弟选择器 */
	    /* .para_one ~ p {
		color: blue;
	    } */
	    .para_one {
		margin: 0;
	    }
	    .para_two {
		display:none;
		margin: 0;
	    }
	    /* 段落一光标悬浮时，选中段落二将其显示 */
	    .para_one:hover + .para_two {
		display: block;
	    }
	    /* 段落二光标悬浮时，显示 */
	    .para_two:hover {
		display:block;
	    }
	</style>
	<body>
	    <p class='para_one'>段落一</p>
	    <p class='para_two'>段落二</p>
	    <p>段落三</p>
	    <p>段落四</p>
	</body>
	</html>
## 三、属性选择器
> 属性选择器
    >* [attr]
        选中具有某个属性的元素，不论其属性值为多少
    >* [attr=value]
        选中具有某个属性，且值为value的元素
    >* [attr^=value]
        选中以某个属性开始的元素
        
*最常用的地方:区分input选择框*

    属性选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>属性选择器</title>
	</head>
	<style>
	    /* 选中三个input框 */
	    /* input {
		color: blue;
	    } */
	    /* 选中第一个和第二个input */
	    /* input[type] {
		color: blue;
	    } */
	    /* 选中第一个input */
	    input[type=text] {
		color: blue;
	    }
	    /* 选中以o开头的属性值 */
	    img[alt^=o] {
		color: yellow;
	    }
	</style>
	<body>
	    <input type="text">
	    <input type="password">
	    <input>
	    <img src="" alt="picture one">
	    <img src="" alt="one">
	</body>
	</html>
## 四、伪类选择器
__在其他选择器的后面使用:连接，实现特殊的效果__
>1. 跟状态相关
        :link 未访问连接
        :hover 用户鼠标悬停
        :active 激活段落
        :visited 已访问连接
        :focus  聚焦
>2. 跟子元素相关
    :first-child
    :last-child
    :nth-child(n),n的取值:  
        *数字:1、2、3、4*  
        *英文字符:odd、even*	

伪类选择器示例：  
  1. 状态相关：

	<!DOCTYPE html>
	<html lang="en">  
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>伪类选择器</title>
	</head>
	<style>
	    /* 未被访问的链接 */
	    .a_one:link {
		color: yellow;
	    }
	    /* 光标悬浮时的链接 */
	    .a_two:hover {
		color: teal;
	    }
	    /* 已访问的链接 */
	    .a_three:visited {
		color: red;
	    }
	    /* 激活时的链接 */
	    .a_four:active {
		color:#ccc;
	    }
	</style>
	<body>
	    <a href="#" class='a_one'>登录1</a>
	    <a href="#" class='a_two'>登录2</a>
	    <a href="#" class='a_three'>登录3</a>
	    <a href="#" class='a_four'>登录4</a>
	</body>
	</html>
   2. 子元素相关：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>伪类选择器-子元素相关</title>
	</head>
	<style>
	    /* 第一个p标签 */
	    p:first-child {
		color: yellow;
	    }
	    /* 最后一个p标签 */
	    p:last-child {
		color: yellow;
	    }
	    /* 第二个p标签 */
	    p:nth-child(2) {
		color: teal;
	    }
	    input:focus {
		background-color: red;
	    }
	</style>
	<body>
	    <p>段落一</p>
	    <p>段落二</p>
	    <p>段落三</p>
	    <p>段落四</p>
	    <input type="text" placeholder="请输入用户名">
	</body>
	</html>
## 五、伪元素选择器
>在其他选择器的后面以::连接，创建元素  _::after，::before_

> 用法：1.导航栏的侧边2.清除浮动  
_jquery： $('.div')  $('#div')_
	
    伪元素选择器示例：
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>伪元素选择器</title>
	</head>
	<style>
	    p::before {
		content: '这个段落的前面';
		color:red;
	    }
	    p::after {
		content: '这个段落的后面';
		color:yellow;
	    }
	</style>
	<body>
	    <p>段落</p>
	</body>
	</html>
# 选择器优先级
1) !important;
        在修改其他组件库的样式的时候使用
        width:200px !important;
2) 选择器的权重:  
    * 1000
            内联style  
    * 100
            id  
    * 10
            类名选择器、伪类选择器、属性选择器  
    * 1
            标签选择器、伪元素选择器
3) css代码的顺序
        谁离选中的页面元素更近，谁生效
    
# 继承
* inherit 继承父元素的属性
* initial 不继承
* unset 不设定
# 浮动布局
1) 默认文档流
    * 元素在页面中显示的顺序跟元素在代码中出现的顺序一致
    * 块级元素独占一行空间
    * 行内元素与其他元素共享一行空间
2) 改变默认布局     _float:left/right_
    * 用法：
        * 使用元素脱离文档流，向左或向右移动，失去对父元素的支撑
        * 使用了浮动的元素的宽高由内容决定
        * 使用了浮动的元素由其他块级元素代替
        * 使用了浮动的元素会在一行从左到右排布，当前行宽度不够时会自动换行 
    * 取值: _left/right_
> 注意:   
    1. 宽高由内容决定  
    2. 使用了浮动的元素，原本的位置会被其他块级元素所替代
    
    案例:
        1、全部浮动
        2、左侧浮动，右侧不浮动
        3、左右浮动，中间不浮动
    阿里面试题:
	清除浮动:
        /*方式一:浮动元素的父元素
        .parent{
            background-color:red;
            overflow:hidden;
        }
        */
        /*方式二 ：浮动元素的父元素
        .parent::after{
            content:'';
            display:block;
            clear:both; 
        }
        */
        /* 方式三：浮动元素的下一个相邻兄弟
        .parent div:lat-child{
            content:''
            clear:both;
        }*/
 
    浮动示例：	
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>左侧浮动</title>
	</head>
	<style>
	    html,body,.wrapper {
		height: 100%;
	    }
	    .left  {
		height: 100%;
		width: 300px;
		background-color:red;
		float: left;
	    }
	    .right {
		height:100%;
		background-color:yellow;
		margin-left: 300px;
	    }
	</style>
	<body>
	    <div class='wrapper'>
		<div class="left"></div>
		<div class="right"></div>
	    </div>
	</body>
	</html>
