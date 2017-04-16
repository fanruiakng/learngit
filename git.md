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