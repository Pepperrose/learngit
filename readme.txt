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