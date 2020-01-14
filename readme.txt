(0)初始化一个Git仓库，使用git init命令。
(1)git add readme.txt  ****使用命令git add <file>，注意，可反复多次使用，添加多个文件；****
(2)git commit -m "wrote a readme file and eigen project"  
****git commit命令，-m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。为什么Git添加文件需要add，commit一共两步呢？因为commit可以一次提交很多文件，所以你可以多次add不同的文件****

(3)修改后,用git status查看工作区的状态
(4)修改后,但是不记得修改了哪些内容,用git diff

(5)版本回退很重要:用git log查看更新的版本,显示从最近到最远的提交日志
git log --pretty=oneline <file> 看到的是commit id

(6)用git reset --hard HEAD^ 回退到上个版本
(7) git reflog 查看回退日志,找到回退的版本的commit id
然后根据git reset --hard <commit id>恢复到原来的版本
***穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。***


(8)工作区和暂存区的概念
本机工作目录,实际修改代码的地方叫做工作区
暂存区是.git目录,里面保存着很多信息,还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD
第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；
第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。

(9)Git跟踪并管理的是修改，而非文件；git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别

(10)场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。


(11)github远程仓库，用来存储和多人协作
