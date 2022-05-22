/*   2022.05.22    */
git架构：工作区->暂存区->版本库区
git add [file]   添加文件进入暂存区
git commit [file] -m    添加文件入库
git status       当前文件状态
git log          查看历史版本
git reset
    在Git中，用HEAD表示当前版本，也就是最新的提交1094adb，
    上一个版本就是HEAD^，上上一个版本就是HEAD^^，往上100个版本写成HEAD~100
    HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
    穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
    要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
git reflog       查看过去命令，用于恢复未来的版本
git diff         查看暂存区和库区文件的不同
git reset HEAD <file> 撤销暂存区修改 
git reset
git checkout     丢弃工作区修改
    场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
    场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，
    第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
    场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。
git rm
git rm test.txt 相当于是删除工作目录中的test.txt文件,并把此次删除操作提交到了暂存区
对于文件删除操作使用git restore --staged <deleted file>,
或先使用git reset head test.txt在暂存区中将暂存区删除操作丢弃,再git checkout -- <delete file>