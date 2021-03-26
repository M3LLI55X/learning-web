1.安装GitWindows客户端
2.注册Gitee账号
3.新建git远程仓库
	点击右上角“+”号，新建仓库
	设置好仓库名称、介绍，将开源选项设置成公开
	点击最下面新建按钮生成git远程仓库
4.本地初始化仓库
	1）进入一个本地文件夹，右击鼠标点击git bush here，进去git命令终端
	2）第一次使用，首先配置账户信息
		git config --global user.name "郝洪辉"
		git config --global user.email "1024543289@qq.com"
	3）初始化仓库
		git init
		执行该命令后，本地文件夹会生成一个.git文件，有此文件的文件夹，即为Git本地仓库
	4）本地文件夹添加文件之后，执行命令，使git追踪到你新添加的文件
		git add * (*号的意思即为所有文件)
	5）提交文件并且设置提交备注信息
		git commit -m "备注信息"
	6）最终将新添加的代码或者文件推到Git远程仓库
		git push -u origin master

5.拉取老师远程Git仓库里的笔记文件
	1）在本地文件夹中右击，点击git bush here打开Git操作终端
	2）先在浏览器中复制老师的Git仓库地址
	   执行命令git clone https://gitee.com/wangyiming11/web2001.git
	3) 想要再次更新本地仓库
	   git pull origin master 即可实现代码或者文件更新