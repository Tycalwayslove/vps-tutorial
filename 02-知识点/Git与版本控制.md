# Git 与版本控制

Git 为一组文件记录历史版本，像有说明文字的存档点。GitHub 是存放远程副本的网站，两者不是同一个程序。Obsidian 不会因为有 Git 仓库就自动替你提交或推送。

| 词 | 本次含义 |
| --- | --- |
| repository / 仓库 | docx 文件夹及隐藏的 .git 历史 |
| commit / 提交 | 一次有说明的本地存档 |
| branch / 分支 | 一条版本发展路线，本次使用 main |
| remote / 远程 | GitHub 上的 vps-tutorial 仓库，别名 origin |
| push / 推送 | 把本地提交传到远程 |
| pull / 拉取 | 把远程更新取回并整合 |
| .gitignore | 告诉 Git 默认忽略哪些未跟踪文件 |

本仓库为 Public。`.gitignore` 不会删除已经提交的秘密，更不能抹去旧提交中的内容。因此必须在 `git add` 和 push 前检查文件及截图。数据库、节点链接和私钥只保存到仓库外。

实操见 [[07-用Obsidian阅读与Git保存]]。

来源：[Pro Git 中文书](https://git-scm.com/book/zh/v2)、[gitignore](https://git-scm.com/docs/gitignore)。
