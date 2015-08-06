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

####标签
	$ git tag tagname            //添加一个标签（最新commit）
	$ git tag tagname commit-id  //给指定版本添加标签
	$ git show tagname           //查看相应标签的信息
	$ git tag                    //查看所有标签
	$ git tag -d tagname         //删除标签
	$ git push origin tagname    //将标签推送到origin远程库
	$ git push origin --tags     //推送全部标签到origin远程库

删除远程库上的标签，需要先删除本地的标签，然后在删除远程库上的标签

	$ git tag -d tagname                  //删除本地标签
	$ git push origin :refs/tags/tagname  //删除远程库标签

####设置别名
	$ git config --global alias.newname oldname //设置别名

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

####stash
stash用于临时的储存

	$ git stash                 //添加到stash
	$ git stash list            //显示stash列表
	$ git stash apply stash@{0} //恢复指定的stash，但是在stash中依然存在
	$ git stash pop             //恢复最上层的stash，并删除stash中的数据
	$ git stash clear           //情况stash

##远程库
####连接Github
生成key

	$ ssh-keygen -t rsa -C "youremail@example.com" //生成key

之后再登录github，在settings中的SSH Keys中添加。  
然后在github中创建一个新仓库，使用以下句子，以添加并推送 
 
	$ git remote add origin git@github.com:sT00ne/Repositoryname.git   //添加名为origin的远程库到对应仓库
	$ git push -u origin master   //推送到远程库
	$ git push origin master      //之后更新使用这句


####克隆远程库  

	$ git clone git@github.com:sT00ne/Repositoryname.git

####其他操作

	$ git remote     //查看远程库信息
	$ git remote -v  //查看远程库详细信息
