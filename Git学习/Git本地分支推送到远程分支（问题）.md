

初始化本地仓库后，然后提交暂存区内容。这时才会有一个master分支。
接着添加一个远程仓库，试着推送本地master到远程仓库的master分支时。

Git提示我如下：
error: failed to push some refs to 'git@github.com:ausle/hungry.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

翻译成中文就是：
推送到远程仓库失败。
更新被拒绝，原因是远程仓库包含你本地没有的内容。
最有可能的原因是，另一个仓库推送了相同的内容。
你需要在推送之前，合并远程。


当我去git pull时，又提示：
refusing to merge unrelated histories
拒绝合并无关的历史。
提示这个原因是，Git发现远程仓库和本地没有一个共同的commit(两个仓库可能不是同一个)，所以Git不让合并操作。
















