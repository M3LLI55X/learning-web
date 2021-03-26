# 动画
## 1.介绍

1. 动画是css3新增，所以可能存在兼容性问题
2. 动画是通过keyframes来定义
3. 动画是不需要任何js基础
   
## 2.语法

1. 动画的定义  一定要写在style标签内部,在一个文件内可以同时定义多个动画 
```
    @keyframes 动画名称 {
        from {} // from是关键帧，动画的开始
        to {} // to是关键帧，动画的结束
    }
      
    @keyframes 动画名称 {
        0% {}
        100% {}
    }

    @keyframes 动画名称 {
        0% {}
        25% {}
        50% {}
        75% {}
        100% {}
    }
```
    使用百分数的好处:可以规定动画执行过程中某一个阶段的样式

2. 动画的使用  
>极简形式  
    只要设置动画名和动画时间即可让动画执行.在需要使用的动画的元素上引用，在样式表内部,可以同时定义多个动画
```
    div {
        margin:10px;
        animation-name:test;
        animation-duration:1s;
    }
```

    animation-name 动画的名称  
        animation-name:test;  
    animation-duration 动画的运行时间  
        秒  
    animation-delay 动画的延迟  
        秒   
        文件首次打开时多少秒再执行动画  
    animation-direction 动画的方向  
        reverse 反方向
        alternate 交替反转
    animation-iteration-count 动画执行的次数
        infinite    无限次
        n   n是一个整数，表示动画执行n次
    animation-fill-mode 动画结束时元素显示的位置
        backwards 动画开始的位置【默认值】
        forwords  动画结束的位置
    animation-timing-function 动画的速度曲线
        linear 匀速
        ease-in 先慢后快
        ease-out 先快后慢
        ease-in-out	先慢后快再慢
        *steps(n) n是一个整数，逐帧播放
    animation-play-state 动画的播放/暂停
        running 播放【默认值】
        paused  暂停
    animation 速写
        animation:animation-name animation-duration  animation-timing-function  
        animation-delay animation-iteration-count   animation-direction animation-fill-mode   animation-play-state  
        animation: move 5s linear infinite;  
