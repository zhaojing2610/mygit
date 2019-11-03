git 使用

1.创建一个空的目录 mkdir mygit
2.到mygit目录下 cd mygit
3.初始化 git init ls -ah(可以看到隐藏的文件)
4.提示：所有的版本控制系统，其实只能跟踪文本文件的改动（图片视频不能定位改了什么）
5.创建readme.txt文件。内容：1
6.git add 将文件的快照放入暂存区域
7.git commit 提交更新,将快照永久性存储到git仓库目录 （ git commit -am 'add commit一起' ）
8.git status 查看命令结果
9.git diff 查看改了些什么（git diff --cached 查看已有缓存改动) (HEAD 查看所有改动) (git diff dev master 两个分支上最新的提交做diff)(git diff master 查看当前分支与master分支的差异)（git diff 738da5 25d135 比较两个历史版本的差异）
10.git log (--pretty=oneline)查看提交日志
11.git reset --hard HEAD^ （commit——id）版本回退
12.git reflog 查看命令历史

工作区和暂存区
工作区：mygit 文件夹就是工作区
暂存区：add后就是暂存区 
git版本库：commit 后就是版本库
每次修改，如果不用git add到暂存区，那就不会加入到commit中
13.git checkout -- readme.txt 工作区撤销修改 --
14.git reset HEAD readme.txt 暂存区撤销修改回到工作区
15.git rm readme.txt 从版本库删除文件 再commit

远程仓库
1.git remote add origin git@server-name:path/repo-name.git 关联一个远程仓库
2.git push -u origin master push到远程仓库

分支
1.git checkout -b dev 创建dev分支并切换到dev (git branch dev、git checkout dev)
2.git merge 切换到master分支 git merge dev
3.git checkout 切换分支（git switch dev）
4.git branch -d dev 删除分支
5.git log --graph 查看分支合并图（git log --oneline简短）
6.merge Fast forward模式 删除分支后，会丢掉分支信息 --no-ff禁用这种模式
7.git stash 储存分支工作
8.git stash apply 恢复 stash
9.git stash drop 删除 stash （git stash pop合并 恢复删除stash）
10.git stash apply stash@{0} 恢复到哪次
11.git cherry-pick <commit> 修复的bug在的分支也修复
12.git branch -D <name> 删除分支
13.git push origin master 推送到远程分支分支
14.git pull origin dev 更新远程分支代码
15.git remote -v 查看远程仓库的信息
16.git checkout -b branch-name origin/branch-name 在本地创建和远程分支对应的分支
17.git branch --set-upstream branch-name origin/branch-name 本地分支与远程分支建立关联
18.git rebase 分叉的提交历史“整理”成一条直线,缺点是本地的分叉提交已经被修改过了
19.git tag <name> 打标签
20.git tag v1.0 f52c63 给对应的commit打tag (git tag -a v0.1 -m "version 0.1 released" f52c63 用-a指定标签名，-m指定说明文字)
21.git show v1.0 查看对应的tag信息
22.git tag -d v0.1 删除本地tag标签
23.git push origin :refs/tags/<tagname> 删除远程分支的tag
24.git push origin --tags 推送全部tag到远程分支
25.git push origin v9.0可以推送一个本地标签
26.git config --global color.ui true 文件名颜色改变
27.忽略某些文件时，需要编写.gitignore 提交版本库生效
28.git add -f App.class 强制添加文件
29.git check-ignore -v App.class 检查该文件添加不成功原因
30.git config --global alias.st status 配置别名
31.echo "# 菜鸟教程 Git 测试" >> README.md 写文件