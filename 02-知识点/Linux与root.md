# Linux 与 root

操作系统负责让硬件和软件一起工作。Windows、macOS 和 Linux 都属于操作系统。本次 tyccc 运行 Debian 12，它是 Linux 的一种发行版；meu 运行 Ubuntu 22.04。

`root` 是 Linux 中权限很高的管理员账号。看到 `root@tyccc:~#`，意味着你正在 tyccc 上以 root 身份操作。不要把提示符也复制进命令。

`/root` 是 root 的个人目录，`/etc` 常放配置，`/usr/local` 常放手动安装的软件，`/tmp` 常放临时文件。开头的 `/` 表示从整个文件系统的根目录开始。

一个简单练习：执行 `pwd` 看当前目录，执行 `ls` 看里面有什么。二者只查看，不删除内容。

root 能改动整个系统，所以先确认“在哪台机器、执行什么”。本教程不把重装系统当作普通的排错步骤；重装可能覆盖已有文件。

继续阅读：[[终端与命令行]]、[[SSH与主机指纹]]。来源：[Debian 官方参考手册](https://www.debian.org/doc/manuals/debian-reference/)。
