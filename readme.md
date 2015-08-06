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

####删除
	$ rm filename              //直接删除
	$ git rm test.txt          //从版本库中删除

####查看状态
	$ cat filename               //查看文件内容
	$ git status                 //查看当前状态
	$ git log                    //查看提交日志
	$ git log --pretty=oneline   //查看简单的提交日志
	$ git log --graph --pretty=oneline //查看有分支图的提交日志

####版本回退
	$ git reset --hard HEAD^     //回退到上一个版本
	$ git reset --hard commit-id //回退到指定版本
	$ git reflog                 //查看历史命令
	$ git diff HEAD -- filename  //查看版本间的区别
	$ git checkout -- filename   //撤销修改 

##连接github
生成key

	$ ssh-keygen -t rsa -C "youremail@example.com" //生成key

之后再登录github，在settings中的SSH Keys中添加。  
然后在github中创建一个新仓库，使用以下句子，以添加并推送 
 
	$ git remote add origin git@github.com:sT00ne/Repositoryname.git   //添加名为origin的远程库到对应仓库
	$ git push -u origin master   //推送到远程库
	$ git push origin master      //之后更新使用这句


克隆远程库  

	$ git clone git@github.com:sT00ne/Repositoryname.git

##分支
####基本操作
一般master中只更新新的版本，平常的更新多使用分支

	$ git checkout -b Branchname     //创建并切换到分支
	$ git checkout Branchname        //切换到分支
	$ git merge Branchname           //合并分支
	$ git branch -d Branchname       //删除分支
	
####分支冲突
当两个分支都经过修改，并提交，则无法合并分支。
在冲突的文件中会出现`<<<<<<<`，`=======`，`>>>>>>>`的标记，修改后即可提交。