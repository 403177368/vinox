# /scripts

## rebase与deploy脚本

/scripts目录下有rebase.js与deploy.js两个脚本。

> npm run rebase:onto:master

该命令将运行/scripts/rebase.js脚本，做如下操作：

1 Rebase local current branch onto remote master branch.

2 将本地当前分支超过remote master branch latest commit的所有commit合并为一条commit，并支持用户输入合并后的commit message。

3 执行git push -f命令用本地当前分支`强制覆盖`远程同名分支。

注意：

若rebase过程中发生代码冲突，脚本将终止运行，之后用户可以：

1、手动解决代码冲突，并运行git rebase –continue命令继续rebase过程。完成后可再运行一遍npm run rebase:onto:master命令。

2、或者运行git rebase –abort命令取消rebase操作。

> npm run deploy

该命令将运行/scripts/deploy.js脚本，做如下操作：

1、在本地基于远程master分支新建一个本地临时分支，名为`combined-[timestamp]`。

2、git pull origin \_config。并使用该分支中的/scripts/deploymentConfig.js配置文件。开发同学可直接在gitlab页面在线修改保存\_config分支中的/scripts/deploymentConfig.js配置文件。

3、将配置文件中指定的几个远程分支依次使用`git pull origin [branchName]`命令merge进上述本地临时分支。

4、若发生代码冲突，建议直接退出该临时分支，由各相关开发同学协商解决各自分支的冲突后再重新运行该脚本。在临时分支上修改代码解决冲突意义不大。

5、若没有发生代码冲突，脚本将根据用户的选择直接运行`git push -f origin [pre/dev/beta]`命令用临时分支的代码`覆盖`远程pre或dev或beta分支的代码。
