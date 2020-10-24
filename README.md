# Git学习

## 1、初始化环境

● 下载Git、注册Github等账号

● 配置本地Git信息

```bash
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

添加了`--global`是针对全局生效的，如果某个仓库需要单独的，只需在这个仓库中使用没有`--global`的命令配置一遍即可

● 生成keygen

```bash
ssh-keygen -t rsa -C "youremail@example.com"
```

将生成的id_rsa.pub中的公钥放到需要提交的服务器上进行验证

## 2、了解Git基本命令

初始化仓库

```bash
git init
```

创建.gitignore文件

```bash
touch .gitignore
# 修改这个文件，将需要忽略的文件名写入
vi .gitignore
```

查看仓库中文件状态

```bash
git status
```

添加当前目录下文件到暂存区

```bash
git add .
# 添加部分文件
git add 文件名|文件夹
```

工作区（working tree），暂存区（index /stage），本地仓库（repository）

将暂存区中的文件进行提交

```bash
git commit -m "本次提交的说明"
```

查看远程仓库

```bash
git remote -v
```

添加远程仓库

```bash
git remote add origin 仓库链接(ssh或https)
```

推送代码

```bash
git push origin master
# origin是远程仓库别名、master是分支名
# 第一次可以多加一个参数
git push -u origin master
```

拉取代码

```bash
git pull origin master
```

克隆代码

```bash
git clone 仓库链接
```

查看文件修改内容

```bash
git diff 文件名
```

查看历史记录

```bash
git log
git log --pretty=oneline
```

查看命令记录

```bash
git reflog
```

版本回退

```bash
# 回退到上一个版本(Git中HEAD代表当前版本)
git reset --hard HEAD^
# 回退到上上个版本
git reset --hard HEAD^^
# 回退到上100个版本
git reset --hard HEAD~100
# 根据版本号回退
git reset --hard 版本号前几位或写全
```

分支管理

```bash
# 创建分支
git branch 分支名
# 切换分支
# git checkout 分支名
git switch -c 分支名
# 可以合写为一条
git checkout -b 分支名
# 查看当前分支
git branch
# 切换回master分支
# git checkout master 或
git switch master
# 合并分支
git merge 分支名
# 删除分支
git branch -d dev
```