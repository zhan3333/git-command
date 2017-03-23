### 基础操作
- `git init` 初始化一个git仓库
- `git status` 查看文件状态
- `git add <file>` 添加文件到版本控制
- `git rm <file> --cached`
- `git commit -m '***'`提交代码
- `git diff` 查看文件修改内容
- `git log --pretty=oneline` 查看文件的修改记录
- `git reset --hard HEAD^` HEAD^为回退到上一个版本,可替换id
- `git reflog` 记录每一次操作的日志
- `git checkout -- file` 丢弃工作区的修改
- `git reset HEAD <file>`清除掉缓存区的文件
- `git remote add origin git@github.com:michaelliao/learngit.git` 本地仓库连接远程仓库
- `git push` 推送本地仓库到远程仓库
- `git push origin master`推送本地master最新版本到origin仓库
- `git clone` 克隆远程仓库到本地

### 分支
- `git checkout -b dev` 新建一个分支并切换
- `git branch` 查看分支列表
- `git branch -d dev`删除一个分支
- `git branch <name>` 创建分支
- `git merge <name>` 合并<name>分支到当前分支
- `git log --graph` 查看分支合并图
- `git merge --no-ff -m "merge with no-ff" dev`生成commit方式合并分支
- `git branch -D <name>` 丢弃name分支
- `git push origin :dev`删除远程仓库分支

### 保存工作区
- `git stash`保存工作区内容
- `git stash list` 列举保存的工作区
- `git stash apply` 恢复stash保存的工作区
- `git stash drop` 删除stash保存的工作区
- `git stash pop`回复保存的工作区并删除这个stash



### 文件错误回退
1. 文件修改后未add回退`git checkout -- file`，丢弃文件file的工作区修改。
2. 文件修改后add，但未commit`git reset HEAD file`缓存区修改撤销
3. 文件已commit但未push，则可以使用`git reset --hard HEAD^`本地仓库回退到上一个版本

### 远程仓库
- `git remote` 查看远程仓库信息
- `git remote -v` 查看远程仓库详细信息
- `git push`推送本地所有分支到远程仓库
- `git push origin <branch-name>`推送branch-name分支到远程仓库
- `git checkout -b dev origin/dev`创建分支并与远程仓库分支连接
- `git branch --set-upstream dev origin/dev`分支设置远程服务器分支连接

### 标签
- `git tag` 查看所有标签
- `git tag v1.0`创建一个标签
- `git tag v0.9 6224937`对commit id对应版本打标签
- `git show v1.0`查看标签详细信息
- `git tag -a v0.1 -m "version 0.1 released" 3628164`标签带描述
- `git tag -d v0.1`删除一个标签
- `git push origin <tagname>`推送标签到远程
- `git push origin --tags` 推送所有标签到远程
- `git push origin :refs/tags/v0.9`删除远程标签

### 忽略文件
- `git check-ignore`检查.gitignore文件是否存在问题
- `git add -f App.class`强制添加文件到git管理
