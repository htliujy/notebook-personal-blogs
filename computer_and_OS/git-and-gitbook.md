# git-and-gitbook

如何使用git。
我比较喜欢的无非就3个命令（三板斧）：

```shell
git add -A
git commit -m ''
git push
```

其他命令，像git pull，git fetch就比较少用，基本我就要靠百度了。

对于github，我想说脏话，为什么忽然github要转换到main主分支，而不是保留原来的master。

现在我要将主分支切回master，又很烦，若是保留默认的main，我的gitbook网站在关联仓库的时候，经常出错，一会儿可以，一会儿不可以的，烦死。
现在我的办法是：先在github上建立一个空的仓库，然后在本地clone后（对，就是clone空的），最后再使用

```shell
git checkout -b master
git branch -d main
```

来实现删除主要分支，切换到master作为主要分支的。

如果远程已经有了main分支的提交，那我要删除远程分支之前，需要将default分支设置成master，然后才能删除成功。

设置default分支，需要在github网页上，点击settings——Branches——选择我们要作为default的分支即可，在我们这个情况下，我是使用了master作为default分支。

删除远程分支的语句如下（切记慎用、慎用、慎用）：

```shell
git push origin --delete main
```

## git 回退历史版本

```shell
git reset --hard [你的commit id]
```

然后推到github上去

```shell
git push -f -u origin master
```

## commit合并

因为我强迫症发作，已有小改动就commit（还push了），导致我的commit log非常的多，需要合并一些不重要的commit，也就是删除一些中间过程记录，让仓库变得简洁些，用rebase命令，当我某个仓库中，我要合并当前commit之前的6次提交，那我就用：

```shell
git rebase -i HEAD~6
```

然后他会弹出让我选择的对话框：
pick 3ca6ec3   '注释**********'

pick 1b40566   '注释*********'

pick 53f244a   '注释**********'

......

根据对话框的提示（非常详尽），那么我们保留第一个为pick，剩下的改用squash，也就是meld into

pick 3ca6ec3   '注释**********'

s 1b40566   '注释*********'

s 53f244a   '注释**********'

......

输入wq可以保存

再然后，还会弹出一个对话框，显示上面这些需要meld（融合）的commit的注释，我们只管写注释，然后仍然是输入wq保存，实现commit提交，

另外，过程中不要太猛，慢慢看，有时候还可以有： git rebase --abort 这样的补救措施等。

搞定后，就可以使用如下命令与远程同步：

```shell
git push origin HEAD --force
```

## git如何clone所有的远程分支

复制自CSDN——[git如何clone所有的远程分支](https://blog.csdn.net/yuanchao99/article/details/39118439)

git clone只能clone远程库的master分支，无法clone所有分支，解决办法如下：

- 找一个干净目录，假设是git_work
- cd git_work
- git clone <http://myrepo.xxx.com/project/.git> ,这样在git_work目录下得到一个project子目录
- cd project
- git branch -a，列出所有分支名称如下：
    remotes/origin/dev
    remotes/origin/release
- git checkout -b dev origin/dev，作用是checkout远程的dev分支，在本地起名为dev分支，并切换到本地的dev分支
- git checkout -b release origin/release，作用参见上一步解释
- git checkout dev，切换回dev分支，并开始开发。

## .gitignore不起作用怎么办

有时候在项目开发过程中，需要移除对一些文件的版本管理，但是添加.gitignore后，发现并未生效，原因是.gitignore只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。那么解决方法就是先把本地缓存删除（改变成未track状态），然后再提交：

```shell
git rm -r --cached .
git add .
git commit -m 'update .gitignore'
```

## 远程仓库

### 删除本地仓库当前关联的无效远程地址，再为本地仓库添加新的远程仓库地址

```shell
git remote -v //查看git对应的远程仓库地址
git remote rm origin //删除关联对应的远程仓库地址
git remote -v //查看是否删除成功，如果没有任何返回结果，表示OK
git remote add origin https://github.com/developers-youcong/Metronic_Template.git //重新关联git远程仓库地址
```

### 修改 .git 配置文件

```shell
cd .git  //进入.git目录
vim config  //修改config配置文件，快速找到remote "origin"下面的url并替换即可实现快速关联和修改
```

## github 提速

因为github的CDN域名污染<sup>[1]</sup>，在host中写入github相关的IP，加速资源上传下载。

### 查询IP地址

查询<www.ipaddress.com>得到：

1. <https://github.com/>
   - 140.82.113.3
2. <https://assets-cdn.github.com/>
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153
3. <http://global.ssl.fastly.net/>
   - 199.232.68.249
4. <codeload.github.com>
   - 140.82.113.10

### 写入host

以如下格式写入host<C:\Windows\System32\drivers\etc>

```text
140.82.113.3：github.com
185.199.110.153：assets-cdn.github.com
140.82.114.9：codeload.github.com
199.232.68.249：global.ssl.fastly.net
```

### 刷新 DNS 缓存

打开命令行（cmd）界面。输入 ipconfig/flushdns 刷新 DNS 缓存即可。

若是后续变慢了，仍然可以使用这个方法，更新IP。

### clone项目

20210224实测结果，变慢了。从70kB/s降低到15kB/s。

参考及引用：

[1] 我的 GitHub 起飞了！-<https://blog.csdn.net/weixin_47080540/article/details/113840504>
