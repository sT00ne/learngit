#Learn Git
##安装git
首先输入`git`，查看是否有安装  
没有则输入`sudo apt-get install git`
##配置git
	$ git config --global user.name "Your Name"  
	$ git config --global user.email "email@example.com"

##创建仓库
创建一个文件夹，之后初始化git
  
	$ mkdir foldername  //创建文件夹
	$ cd foldername     //进入改文件夹
	$ pwd               //显示路径
	$ git init          //初始化Git  

##基本操作
####提交
	$ git add filename         //添加文件
	$ git commit -m "SUMMARY"  //提交文件，并作出说明
####查看状态
	$ cat filename               //查看文件内容
	$ git status                 //查看当前状态
	$ git log                    //查看提交日志
	$ git log --pretty=oneline   //查看简单的提交日志
	$ git log --graph --pretty=oneline //查看有分支图的提交日志
####版本回退
	$ git reset --hard HEAD^


