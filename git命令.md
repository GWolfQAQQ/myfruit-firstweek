### git命令

| 命令行                                                       | 命令行作用                   |
| :----------------------------------------------------------- | :--------------------------- |
| git config [--global] user.name <"user.name">                | 查看你的名字                 |
| git config [--global] user.email <"user.email">              | 查看你的email                |
|                                                              |                              |
| git clone <url>                                              | 克隆文件                     |
| git init                                                     | 初始化                       |
| git status                                                   | 显示状态                     |
|                                                              |                              |
| git add <文件名> [-A]                                        | 文件到缓冲区                 |
| git commit [-m] <"要输入的话">                               | 文件到本地仓库               |
|                                                              |                              |
| git log [--oneline]                                          | 显示所有版本信息             |
| git reflog                                                   | 查看所有分支的所有操作记录   |
| git reset --hard 版本号                                      | 回滚到某版本                 |
|                                                              |                              |
| git remote add origin (远程主机名) 地址  https://github.com/kerry1212/tthgh.git | 连接远程主机                 |
| git push -u <远程主机名> <本地分支名master> [: <远程分支名>] | 文件到远程仓库               |
| git fetch origin master                                      | 文件从远程仓库到远程仓库副本 |
|                                                              |                              |
| git branch <新建分支名>                                      | 新建分支                     |
| git checkout -b <分支名>                                     | 新建并切换到分支             |
| git merge 要合并的分支                                       | 合并                         |

