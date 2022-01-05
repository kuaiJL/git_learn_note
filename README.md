# git_learn_note
A repository of learning git
#21/8/30

git

情况：xiejiang@xiejiang-B460M:~/component-doc/kjl/winged-components-web$ git branch -a

- dev master remotes/origin/HEAD -> origin/master remotes/origin/components-doc remotes/origin/kuaijinliang/components-doc remotes/origin/master
- 本地分支dev关联了remotes/origin/components-doc，可以直接push到其。
- but我想push到远程指定分支，例如remotes/origin/kuaijinliang/components-doc
- 此时则用命令   :  **git push origin dev:kuaijinliang/components-doc**

现在的情景是，你已经在本地创建了一个Git仓库后，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步，这样，GitHub上的仓库既可以作为备份，又可以让其他人通过该仓库来协作，真是一举多得。
首先，登陆GitHub，然后，在右上角找到“Create a new repo”按钮，创建一个新的仓库：
github-create-repo-1
在Repository name填入learngit，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库：
github-create-repo-2
目前，在GitHub上的这个learngit仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。
现在，我们根据GitHub的提示，在本地的learngit仓库下运行命令：
$ git remote add origin git@github.com:michaelliao/learngit.git
请千万注意，把上面的michaelliao替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。
添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。
下一步，就可以把本地库的所有内容推送到远程库上：
$ git push -u origin master
#!!!!!!!!!!!  这一步可能出错：
1.没有添加ssh-key在GitHub中，首先本地新建ssh-key，建好了可以在C:/user/kjl/.ssh看到，复制.pub的内容，在github中添加ssh-key。
2.然后继续，可能还会出错：
ssh: connect to host github.com port 22: Connection timed out
fatal: Could not read from remote repository.
22：端口不能用，改成443.
如上参考：https://blog.csdn.net/nightwishh/article/details/99647545   ，  https://blog.csdn.net/u013778905/article/details/83501204  ，https://www.jianshu.com/p/e786a8f7f022

#拉去远程仓库指定分支
git clone -b dev @github.......

新建分支并切换到指定分支

git checkout -b 本地分支名 origin/远程分支名
