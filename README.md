```bash
#git配置
name: git config --global user.name "yushuhua"
email: git config --global user.email "3026967662@qq.com"
#git使用
git status: 查看当前仓库的状态
git init: 初始化仓库
刚刚添加到git中的文件处于未跟踪状态
未跟踪-->暂存: 
git add (filename) 将文件切换到暂存的状态
git add * 将所有已修改(未跟踪)的文件暂存
暂存-->未修改:
git commit -m "xxx" (字符串内通常是日志)将暂存的文件存储到仓库中
git commit -a -m 'xxx' 提交所有已修改的文件(未跟踪的文件不会提交)
未修改-->修改
修改代码后，文件会变成修改状态
#常用命令
git restore (filename) 恢复文件
git restore --staged (filename) 取消暂存状态
git rm (filename) 删除文件
git rm (filename) -f 强制删除文件
git mv (filename) (new filename) 移动文件(重命名)
#分支
git在存储文件时，每一次代码的提交都会常见一个与之对应的节点，git就是通过一个一个节点来记录代码的状态的，节点会构成一个树状结构，意味着这个树会存在分支，默认情况下仓库只有一个分支，命名为master，在使用git时，可以创建多个分支，分支与分支之间相互独立，在一个分支上面修改代码不会影响其他分支
git branch 查看当前分支
git branch (branch name) 创建新的分支
git branch -d (branch name) 删除分支
git switch (branch) 切换分支
git switch -c (branch) 创建并切换分支
在开发中，都是在自己的分支中编写代码，代码编写完成后，再将自己的分支合并到主分支上
git merge (branch name) 合并分支
#远程仓库
远程的git仓库和本地的本质没有什么区别，不通电在于远程的仓库可以被多人同时访问使用，方便我们协同开发。在实际工作中，git的服务器通常由公司搭建内部使用或是购买一些公共的私有git服务器，学习阶段，直接使用一些开放的公共git仓库，目前常用的库有两个：github和gitee
将本地库上传github:
git remote add (remote name) (url)
git branch -M main 修改分支的名字为main
git push -u origin main 将代码上传到服务器上
将本地库上传gitee:
git remote add eng https://gitee.com/hey_lin/suki.git
git push -u eng main
#远程库操作的命令
git remote 列出当前关联的远程库
git remote add (远程库名) (url) 关联远程仓库
git remote rmove (远程库名) 删除远程仓库
git push -u (远程库名) (分支名) 向远程库推送代码，并和当前分支关联
git clone (url) 从远程库下载代码
git push 如果本地的版本低于远程库，push默认推不上去
git push (远程库名) (本地分支):(远程分支)
git fetch 要想推送成功，必须保持版本一致，fetch会从远程下载所有代码，但是它不会将代码和当前分支自动合并，使用git fetch拉取代码后，必须要手动对代码进行合并
git pull 从服务器上拉取代码并自动合并
#tag标签
当头指针没有执行某个分支的头部时，这种状态我们称为分离头指针(HEAD detached)，分离头指针状态下也可以操作修改代码，但是这些操作不会出现在任何的分支上，所以注意不要在分离头指针的状态下来操作仓库
git switch -c (分支名) (提交ID)若非要回到后边的节点对代码进行操作，可以选择创建分支后在进行操作
可以为提交记录设置标签，设置标签以后，可以通过标签快速的识别出不同的开发节点:
git tag
git tag (版本)
git tag (版本) (提交ID)
git push (远程库名) (标签名)
git push (远程库名) --tags
git tag -d (标签名) 删除标签
git push (远程库名) --delete (标签名) 删除远程标签
#gitignore
默认情况下，git会监视项目中的所有内容，但有些内容比如node_modules目录中的内容，我们不希望它被git所管理，所以可以在项目中添加一个新的.gitignore文，来设置哪些需git忽略的文件
#github的静态页面
在github中，可以将自己的静态页面部署到github中，它会给我门提供一个地址使我们的页面变成一个真正的网站，可以供用户访问
要求:
静态页面的分支必须叫做gh-pages
若希望页面可以通过xxx.github.io访问，则需要将库的名字配置为xxx.github.io
```

