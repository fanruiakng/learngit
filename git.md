- ##### 配置git
    $ git config --global user.name "Your Name"
    
    $ git config --global user.email "email@example.com"

- ##### 创建repository
    $ mkdir learngit

    $ cd learngit
    
    $ git init
    
- ##### 添加文件到暂存区
    $ git add readme.txt
- #####  文件提交到仓库
    $ git commit -m "wrote a readme file"

- ##### 仓库当前的状态
    $ git status

- ##### 查看改变
    $ git diff readme.txt  

    git diff <file> 等价于 git diff HEAD -- <file>, 
    
    HEAD为任意版本号

- ##### 历史记录
    $ git log

    简要记录：$ git log --pretty=oneline
- ##### 回退至上一版本
    $ git reset --hard HEAD^
- ##### 命令记录
    $ git reflog    以便确定要回到未来的哪个版本

- ##### 丢弃工作区修改
    $ git checkout -- readme.txt

- ##### 丢弃暂存区修改
    $ git reset HEAD readme.txt
- ##### 从版本库删除
    $ git rm test.txt

    $ git commit -m "remove test.txt"
- ##### 撤销误删
    $ git checkout -- test.txt

 #### 远程仓库
 
 - ##### 创建ssh key
    $ ssh-keygen -t rsa -C "youremail@example.com"

登录github 用户设置 添加ssh key  

- ##### 关联远程库
   git remote add origin git@server-name:path/repo-name.git
- ##### 首次推送主分支并与远程分支关联
    git push -u origin master

- ##### 以后的提交
    git push origin master

- ##### 克隆远程
    git clone

#### 分支管理
- ##### 创建并切换分支
    $ git checkout -b dev ==$ git branch dev$ git checkout dev

- ##### 查看当前分支
    $ git branch
- ##### 合并分支到当前分支
    $ git merge dev  

- ##### 删除分支
     $ git branch -d dev

- ##### 查看分支合并图
    git log --graph
- ##### --no-ff（Fast forward）方式的git merge
$ git log --graph --pretty=oneline --abbrev-commit

- ##### “储藏”工作现场
$ git stash
- ##### 查看工作现场
    $ git stash list
- ##### 恢复stash内容并不删除
 git stash apply

- ##### 删除工作现场
 git stash drop
- ##### 恢复并删除stash
 git stash pop
- ##### 删除未合并分支
    git branch -D <name>

- ##### 查看远程库的信息
$ git remote -v     

#### 多人合作

首先，可以试图用git push origin branch-name推送自己的修改；

如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

如果合并有冲突，则解决冲突，并在本地提交；

没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！

如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。

- ##### 在本地创建和远程分支对应的分支
 git checkout -b branch-name origin/branch-name

- ##### 建立本地分支和远程分支的关联
 git branch --set-upstream branch-name origin/branch-name

 ##### 创建标签
 1.首先，切换到需要打标签的分支上
 
 2.git tag <name>
 
 1.$ git log --pretty=oneline --abbrev-commit
 
 2.$ git tag v0.9 6224937
 
 还可以创建带有说明的标签，用-a指定标签名，-m指定说明文字
 
 - ##### 删除标签
    $ git tag -d v0.1
- ##### 推送某个标签到远程
 git push origin <tagname>

- ##### 推送全部尚未推送到远程的本地标签
$ git push origin --tags

##### 删除远程标签
1.本地删除

$ git tag -d v0.9

2.远程删除

$ git push origin :refs/tags/v0.9

- ##### 让Git显示颜色
$ git config --global color.ui true

##### 忽略特殊文件
https://github.com/github/gitignore5