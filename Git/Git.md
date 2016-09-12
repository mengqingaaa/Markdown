# 基本命令

### `git reset`
`reset` 命令把当前分支指向另一个位置，并且有选择的变动索引和工作目录。
也克用来从历史仓库中复制文件到索引，而不动工作目录。
- #### `git reset -- <files>`
    用来撤销最后一次 `git add <files>`，也可以用 `git reset`撤销所有暂存区域文件。

### `git checkout`
`checkout` 命令用于从历史提交（或者暂存区域）中拷贝文件到工作目录， 也克用于切换分支。
- ### `git checkout -- <files>`
    把文件从暂存区域复制到工作目录，用来丢弃本地修改。

### `git diff`
![git diff][1]



[1]: http://obfgdhijv.bkt.clouddn.com/diff.svg


# 运行机制

### 暂存操作
暂存操作会
- 对每一个文件计算校验和（即`SHA-1`哈希字串）
- 然后把当前版本的文件快照保存到 Git 仓库中（Git 使用`blob`类型的对象存储这些快照）；
- 并将校验和加入暂存区域。

### 提交操作
当使用 `git commit` 新建一个提交对象前
- Git 会先计算每一个子目录的校验和；
- 然后在 Git 仓库中将这些目录保存为树 `tree` 对象。
- 之后 Git 创建提交对象，除了包含相关的提交信息意外，还包含指向这个树对象（项目根目录）的指针，因此可以在将来需要的时候，重现此次快照的内容了。

![commit_tree][commit_tree]
![commit_link_list][commit_link_list]


[commit_tree]: http://obfgdhijv.bkt.clouddn.com/commit-and-tree%5B1%5D.png
[commit_link_list]: http://obfgdhijv.bkt.clouddn.com/commits-and-parents%5B1%5D.png


# Git 分支
Git 分支，从本质上仅仅是个指向 `commit` 对象的可变指针。
Git 会使用 `master` 作为分支的默认名字。
`HEAD` 指针是一个指向正在当前的本地分支的指针。