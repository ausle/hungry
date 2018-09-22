###什么是分支?

暂存操作，也就是git add操作，会把当前版本的文件快照保存到git仓库中，保存的形式是以blob类型的对象存储这些快照。
git commit提交创建commit对象之前，会创建一个树对象，该树对象记录目录树的内容以及各个文件对应blob对象索引。
而创建的commit对象，则有一个指向树对象的索引。
多次提交后，这次的提交对象commit对象则包含一个指向上次提交对象的指针。

总结的说：
commit有一个指向树对象的指针，树对象包含各个文件存储的blob对象的索引。
而每一次提交，该次的commit对象就有指针指向上次的commit对象。

分支，本质上就是一个指向commit对象的可变指针。而且在每次提交，都会自动前移。
**Git使用master作为分支的默认名字**。
**HEAD是一个指向你正在工作的本地分支指针。**
>git branch创建分支
>git checkout切换分支


###远程分支
git clone某个远程仓库时，Git会自动为你将该仓库命名为origin，建立一个master分支的指针。在本地命名为origin/master。
接着，Git会建立一个属于你自己的本地master分支，和origin/master分支指向相同的位置。

git fetch origin来同步远程服务器上的数据到本地。如果服务器上master分支数据更新了的话。

推送本地分支到远程分支：
git push origin serverfix，把本地serverfix分支推送到origin/serverfix。
git push origin serverfix:awesomebranch，serverfix分支推送到awesomebranch远程分支。

git fetch下载到的新的远程分支，你无法编辑。你只是有一个你无法移动的该分支的指针。
假如该分支为origin/serverfix。
你可以进行合并分支，
>git merge origin/serverfix

如果要有一份自己的分支，可以新建一个分支，其内容与origin/serverfix一致。自动将推送和抓取数据定位到该远程分支上了。
>git checkout -b serverfix origin/serverfix




