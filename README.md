# GitCommonCommands
## Git的常用命令的笔记:

![] (http://www.baidu.com/img/bdlogo.gif)

按Tab键：补全命令

ll：查看当前目录下的所以文件（不包含隐藏）

ll -lA:查看当前目录下所以的文件（包含隐藏）

cd + 目录：切换目录（cd ..:回到上级目录）

cat + 文件路径：查看文件里的内容

pwd：查看当前在那个目录下



### 设置签名：（项目级别）
git config user.name + 用户名：设置用户名（项目级别）

git config user.email + 邮箱账号：设置邮箱账号（项目级别）

### 设置签名：（系统级别）
git config --global user.name + 用户名：设置用户名

git config --global user.email + 邮箱账号：设置邮箱账号


git status:查看当前状态（红色没有添加到缓存区，绿色表示已经添加到缓冲区）

git init:初始化仓库

git add + 想要提交的更改的文件 或者 git add . 所有的文件：提交文件到缓存区

git commit + 文件名：提交文件，后会打开一个vim编辑器编辑的日志文件，在里面写日志（可以写中文，不指定文件=提交所以文件）

git rm --cached + 文件名：移除某文件（缓存区）

git log:查看提交的记录（git log --pretty=onelin:一行显示记录（或者git log --onelin）git reflog:显示回退的步数）

git reset --hard + 哈希值（局部索引）：回退到某个版本（后退和前进都是一样）

rm + 文件名：删除文件（如果想回退，一定要先添加到缓存区。如果要找回就用“git reset --hard + 哈希值（局部索引）”）

git diff +文件名:比较文件的差异（git diff +局部索引+文件名：历史中的版本的文件和现在的文件的差异）

git remote -v:查看当前所以远程地址的别名

git remote add +别名 +远程仓库的地址：创建远程仓库地址的别名

git push -u +地址别名 +分支名：推送（把本地仓库中的文件同步到远程仓库中）（如果是别人创建的仓库，要加入团队后才能推送）

邀请别加入团队：点击GitHub上的仓库的Settings -->再点击Collaborators -->再输入你要邀请的人的用户名或者邮箱地址按确定 -->拷贝链接地址-->打开链接并确定加入团队

git clone +远程仓库的地址：克隆某人的仓库（还带有：分支名和地址别名，并帮你初始化本地仓库）

git pull +远程库地址别名 +远程分支名=fetch(拉取)+merge（合并）（注意：如果有冲突就像合并分支那样解决）

git fetch +远程库地址别名 +远程分支名：拉取远程仓库

git checking +远程库地址别名 / 远程分支名:切换到拉取的仓库（可以审查代码）

git merge +远程库地址别名 / 远程分支名：合并拉取远程仓库




### vim编辑器的用法（默认是命令模式）

vim + 文件名.格式：创建文件

i:切换输入模式

Esc:返回命令模式后按“：”再输入命令

wq:保存并退出

set nu:显示行号（要在：（命令模式）下）

空格：向下翻页

b：向上翻页

q：退出分页




### 分支：
git branch -v:查看当前的分支

git branch [分支名]_fix:创建新的分支

git checkout +分支名：切换分支

合并分支（没冲突（一般回到主分支））：git merge +别的分支的分支名

合并分支（有冲突（一般回到主分支））：
  （1）git merge +别的分支的分支名
  （2）交流
  （3）用vim编辑冲突的文件（1.把自动生成的内容删除 2.修改里的内容）
  （4）再提交文件-git commit -m "日志内容"（不要加文件名）

git branch -d + 分支名：删除某分支（要切换别的分支去删除，不能自杀） 






### 把项目托管到GitHub的步骤
1.git init:初始化仓库

2.在GitHub上创建一个远程仓库

3.复制远程仓库的HTTPS地址

4.git add README.md:创建项目的说明文档（放到缓存区）

5.git commit -m "first commit+日志内容":提交所以文件

6.在本地创建远程仓库别名（git remote add origin + 仓库地址）

7.git push -u origin master:把本地仓库中的文件同步到远程仓库中

8.从GitHub下载项目到本地（git clone + 项目地址）

### Github提交更新的代码：
1.git status：查看更改了哪些文件的代码

2.git add 你想要提交的更改的文件 或者 git add . 所有的文件

3.git commit -m ‘提交信息’把本地仓库暂存区的文件提交到本地仓库

4.git push -u origin master：把本地仓库中的文件同步到远程仓库中

