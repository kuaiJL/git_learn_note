# git_learn_note
A repository of learning git
#21/8/30

git

情况：xiejiang@xiejiang-B460M:~/component-doc/kjl/winged-components-web$ git branch -a

- dev master remotes/origin/HEAD -> origin/master remotes/origin/components-doc remotes/origin/kuaijinliang/components-doc remotes/origin/master
- 本地分支dev关联了remotes/origin/components-doc，可以直接push到其。
- but我想push到远程指定分支，例如remotes/origin/kuaijinliang/components-doc
- 此时则用命令   :  **git push origin dev:kuaijinliang/components-doc**

