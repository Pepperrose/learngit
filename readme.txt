1.创建版本仓库
 $mkdir learngit
 $cd learngit
 $pwd
2.把目录变成git可以管理的仓库
 $git init
3.用个git add 把文件添加到仓库
 $git add readme.txt
4.用 git conmit
 $git commit -m"git order"
5.git status 查看仓库的当前状态
6.用git diff 查看修改过什么
 git diff readme.txt
7.git log 查看历史记录
8.git reset --hard HEAD^(退回上一个版本) / HEAD^(退回到上上个版本)
9.git reflog 用来记录没一条命令

工作区 和 暂存区

前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：
第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；

第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。

10.cat readme.txt 显示readme.txt内容
11.用git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别

	先修改  再添加


删除文件
	1、rm 用于删掉文件管理器中的文件 
	2、如果确定删除 
	   	git rm test.txt
	   	git commit -m"remove test.txt"
       如果是误删，要恢复的话
       	git checkout -- test.txt

远程仓库
	第一步创建SSH Key，在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa 和 id_rsa.pub 这两个文件，如果已经有了，可以直接跳到下一步。如果没有，打开Shell(Window 下打开 Git Bash)，创建SSH Key：
		$ ssh-keygen -t rsa -C "youremail@example.com"

	如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

	第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面,然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容